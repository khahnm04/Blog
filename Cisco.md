Để PC3 tự động nhận VLAN và địa chỉ IP khi cắm vào mạng, bạn cần cấu hình VLAN, IP, và DHCP sao cho hệ thống tự động gán VLAN và cấp IP qua DHCP. Dựa trên sơ đồ mới, bạn đã thêm PC3 vào Switch1 (qua cổng Fa0/3). Tôi sẽ hướng dẫn bạn cấu hình để PC1, PC2, và PC3 tự động nhận VLAN và IP khi cắm vào.

### Tóm tắt cấu hình và thứ tự thực hiện
1. **Cấu hình VLAN**: Tạo và gán VLAN cho các nhánh (mỗi nhánh một VLAN).  
   - PC1 và PC3 (trên Switch1): VLAN 10.  
   - PC2 (trên Switch2): VLAN 20.  
   - Sử dụng VTP (nếu cần) để đồng bộ VLAN giữa các switch.

2. **Cấu hình IP**: Gán IP cho interface VLAN trên eSW (gateway).  

3. **Cấu hình DHCP**: Cấu hình DHCP pool để cấp IP tự động cho PC1, PC2, và PC3.

4. **Đảm bảo tự động nhận VLAN**: Sử dụng chế độ trunk và access để tự động gán VLAN khi cắm PC.

---

### Hướng dẫn chi tiết

#### 1. Cấu hình VLAN
##### Trên eSW (Core Switch)
- Tạo VLAN 10 (cho PC1 và PC3) và VLAN 20 (cho PC2):
  ```
  conf t
  vlan 10
   name VLAN10_Nhanh1
  vlan 20
   name VLAN20_Nhanh2
  exit
  ```
- Cấu hình cổng Fa0/1 (trunk với Switch1, truyền VLAN 10):
  ```
  interface FastEthernet0/1
   switchport mode trunk
   switchport trunk allowed vlan 10
   no shutdown
  exit
  ```
- Cấu hình cổng Fa0/2 (trunk với Switch2, truyền VLAN 20):
  ```
  interface FastEthernet0/2
   switchport mode trunk
   switchport trunk allowed vlan 20
   no shutdown
  exit
  ```

##### Trên Switch1
- Cấu hình cổng Fa0/1 (trunk với eSW, VLAN 10):
  ```
  conf t
  interface FastEthernet0/1
   switchport mode trunk
   switchport trunk allowed vlan 10
   no shutdown
  exit
  ```
- Cấu hình cho tất cả các cổng từ Fa0/2 -> Fa0/24 (access cho PC1, VLAN 10):
  ```
  conf t
   interface range FastEthernet0/2 - 24
    switchport mode access
    switchport access vlan 10
    no shutdown
   exit
  ```

##### Trên Switch2
- Cấu hình cổng Fa0/1 (trunk với eSW, VLAN 20):
  ```
  conf t
  interface FastEthernet0/1
   switchport mode trunk
   switchport trunk allowed vlan 20
   no shutdown
  exit
  ```
- Cấu hình cho tất cả các cổng từ Fa0/2 -> Fa0/24 (access cho PC2, VLAN 20):
  ```
  conf t
   interface range FastEthernet0/2 - 24
    switchport mode access
    switchport access vlan 10
    no shutdown
   exit
  ```

---

#### 2. Cấu hình IP
##### Trên eSW
- Gán IP cho interface VLAN 10 (gateway cho PC1 và PC3):
  ```
  conf t
  interface vlan 10
   ip address 192.168.10.1 255.255.255.0
   no shutdown
  exit
  ```
- Gán IP cho interface VLAN 20 (gateway cho PC2):
  ```
  interface vlan 20
   ip address 192.168.20.1 255.255.255.0
   no shutdown
  exit
  ```

---

#### 3. Cấu hình DHCP
##### Trên eSW
- Tạo DHCP pool cho VLAN 10 (cho PC1 và PC3):
  ```
  conf t
  ip dhcp pool VLAN10_POOL
   network 192.168.10.0 255.255.255.0
   default-router 192.168.10.1
   dns-server 192.168.17.254
  exit
  ```
- Tạo DHCP pool cho VLAN 20 (cho PC2):
  ```
  ip dhcp pool VLAN20_POOL
   network 192.168.20.0 255.255.255.0
   default-router 192.168.20.1
   dns-server 192.168.17.254
  exit
  ```
- Loại trừ IP gateway:
  ```
  ip dhcp excluded-address 192.168.10.1
  ip dhcp excluded-address 192.168.20.1
  ```

---

#### 4. Đảm bảo tự động nhận VLAN và IP
- **VLAN tự động**: Khi cắm PC3 vào Switch1 (Fa0/3), cổng đã được cấu hình ở chế độ access VLAN 10, nên PC3 sẽ tự động thuộc VLAN 10 mà không cần cấu hình thủ công thêm (trừ khi switch không nhận diện tự động, bạn cần kiểm tra VTP).
- **IP tự động**: Khi PC3 được đặt chế độ DHCP, nó sẽ tự nhận IP từ DHCP pool VLAN 10.

##### Cấu hình VTP (tùy chọn để đồng bộ VLAN)
- **Trên eSW** (làm VTP Server):
  ```
  conf t
  vtp mode server
  vtp domain Cisco
  vtp version 2
  exit
  ```
- **Trên Switch1 và Switch2** (làm VTP Client):
  ```
  conf t
  vtp mode client
  vtp domain Cisco
  vtp version 2
  exit
  ```

---

### Kiểm tra và lưu cấu hình
- **Trên eSW**:
  ```
  show ip dhcp binding
  show vlan brief
  show interface trunk
  write
  ```
- **Trên Switch1 và Switch2**:
  ```
  show vlan brief
  show interface trunk
  write
  ```

---

### Cấu hình PC
- **PC1**: Desktop > IP Configuration > Chọn DHCP.
- **PC2**: Desktop > IP Configuration > Chọn DHCP.
- **PC3**: Desktop > IP Configuration > Chọn DHCP.

---

### Kết quả mong đợi
- **PC1 và PC3** (VLAN 10): Nhận IP từ dải 192.168.10.2 đến 192.168.10.254, gateway 192.168.10.1.
- **PC2** (VLAN 20): Nhận IP từ dải 192.168.20.2 đến 192.168.20.254, gateway 192.168.20.1.
- Khi cắm PC3 vào Switch1 (Fa0/3), nó sẽ tự động thuộc VLAN 10 và nhận IP từ DHCP nếu cấu hình đúng.

### Kiểm tra nếu không nhận IP
- Đảm bảo cáp nối đúng (màu xanh).
- Kiểm tra chế độ DHCP trên PC.
- Xem trạng thái cổng: `show ip interface brief` trên eSW.
- Kiểm tra binding DHCP: `show ip dhcp binding`.

Hãy thử và cho tôi biết kết quả nhé! Nếu cần thêm hỗ trợ (như access-list), tôi sẽ tiếp tục giúp.
