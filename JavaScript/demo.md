
# Học JavaScript: Hàm, Object và Các Phương Thức Mảng

JavaScript là ngôn ngữ lập trình mạnh mẽ, phổ biến trong phát triển web. Bài học này tập trung vào các loại hàm, cách làm việc với object, và các phương thức mảng hữu ích. Hãy cùng khám phá qua các ví dụ thực tế!

## 1. Hàm trong JavaScript

Hàm là chương trình con thực hiện một công việc cụ thể. Có 2 loại hàm chính:
- **Hàm built-in**: Có sẵn trong JavaScript (VD: `console.log()`, `alert()`).
- **Hàm tự định nghĩa**: Do lập trình viên tự viết.

### 1.1. Các cách viết hàm

JavaScript hỗ trợ 3 kiểu hàm: **Declaration Function**, **Expression Function**, và **Arrow Function**.

#### a. Declaration Function (Hàm định nghĩa)
- Có **hoisting** (gọi hàm trước khi khai báo được).
- Sử dụng đối tượng `arguments`.

```javascript
function sum() {
    let total = 0;
    for (const number of arguments) {
        total += number;
    }
    return total;
}
console.log(sum(10, 20, 30)); // Kết quả: 60
```

#### b. Expression Function (Hàm biểu thức)
- Không có hoisting (gọi trước khai báo sẽ lỗi).
- Sử dụng `arguments`.

```javascript
const sum = function() {
    let total = 0;
    for (const number of arguments) {
        total += number;
    }
    return total;
};
console.log(sum(10, 20, 30)); // Kết quả: 60
```

#### c. Arrow Function (Hàm mũi tên)
- Không có `arguments` (dùng `...` để nhận tham số).
- Không có hoisting.
- Cú pháp ngắn gọn.

```javascript
const sum = (...numbers) => {
    let total = 0;
    for (const number of numbers) {
        total += number;
    }
    return total;
};
console.log(sum(10, 20, 30)); // Kết quả: 60
```

Ví dụ ngắn gọn:

```javascript
const hello = fullName => `Xin chào ${fullName}!`;
console.log(hello("Nguyen Van A")); // Kết quả: Xin chào Nguyen Van A!
```

## 2. Làm việc với Object

Object là tập hợp các cặp key-value để lưu trữ dữ liệu.

### 2.1. Thêm key mới vào object
Dùng dấu chấm (`.`) hoặc ngoặc vuông (`[]`).

```javascript
const infoUser = {
    fullName: "Le Van A"
};
infoUser.phone = "0123456789"; // Cách 1
infoUser["phone"] = "0123456789"; // Cách 2
console.log(infoUser); // { fullName: "Le Van A", phone: "0123456789" }
```

### 2.2. Xóa key khỏi object
Dùng từ khóa `delete`.

```javascript
const infoUser = {
    fullName: "Le Van A",
    phone: "0123456789"
};
delete infoUser.phone;
console.log(infoUser); // { fullName: "Le Van A" }
```

## 3. Các phương thức mảng

JavaScript cung cấp nhiều phương thức mảng tiện lợi:

### 3.1. forEach()
Duyệt qua từng phần tử để thực hiện hành động.

```javascript
const monHoc = [
    { ten: "Toán", diem: 8.5 },
    { ten: "Lý", diem: 7.5 },
    { ten: "Hóa", diem: 5.5 },
    { ten: "Tin", diem: 9.5 }
];

monHoc.forEach(item => {
    let hocLuc = "";
    if (item.diem >= 8) hocLuc = "Giỏi";
    else if (item.diem >= 6.5) hocLuc = "Khá";
    else if (item.diem >= 4) hocLuc = "Trung bình";
    else hocLuc = "Yếu";
    item.hocLuc = hocLuc;
    delete item.diem;
});
console.log(monHoc);
// [{ ten: "Toán", hocLuc: "Giỏi" }, { ten: "Lý", hocLuc: "Khá" }, ...]
```

### 3.2. every()
Kiểm tra **tất cả** phần tử thỏa mãn điều kiện.

```javascript
const hocSinhGioi = monHoc.every(item => item.diem >= 8);
console.log(hocSinhGioi); // true nếu tất cả điểm >= 8
```

### 3.3. some()
Kiểm tra **ít nhất một** phần tử thỏa mãn điều kiện.

```javascript
const oLaiLop = monHoc.some(item => item.diem < 4);
console.log(oLaiLop); // true nếu có ít nhất một điểm < 4
```

### 3.4. find()
Tìm **phần tử đầu tiên** thỏa mãn điều kiện.

```javascript
const listUser = [
    { fullName: "Le Van A", email: "levana.123@gmail.com" },
    { fullName: "Le Van B", email: "levanb.123@gmail.com" }
];
const registerAccount = { fullName: "Le Van AAA", email: "levana.123@gmail.com" };
const existAccount = listUser.find(item => item.email === registerAccount.email);
if (existAccount) {
    console.log("Email đã tồn tại!");
}
```

### 3.5. filter()
Tìm **tất cả** phần tử thỏa mãn điều kiện.

```javascript
const keyword = "Le Van A";
const listUserFilter = listUser.filter(item => item.fullName === keyword);
console.log(listUserFilter);
// [{ fullName: "Le Van A", email: "levana.123@gmail.com" }, ...]
```

### 3.6. map()
Tạo mảng mới từ mảng gốc.

```javascript
const mangMoi = monHoc.map(item => {
    let hocLuc = "";
    if (item.diem >= 8) hocLuc = "Giỏi";
    else if (item.diem >= 6.5) hocLuc = "Khá";
    else if (item.diem >= 4) hocLuc = "Trung bình";
    else hocLuc = "Yếu";
    return { ten: item.ten, hocLuc };
});
console.log(mangMoi);
// [{ ten: "Toán", hocLuc: "Giỏi" }, { ten: "Lý", hocLuc: "Khá" }, ...]
```

### 3.7. reduce()
Tính toán và trả về một giá trị duy nhất.

```javascript
const numbers = [2, 5, 8, 10, 15];
const result = numbers.reduce((sum, item) => sum + item, 0);
console.log(result); // 40
```

Tính tuổi trung bình:

```javascript
const listUser = [
    { fullName: "Le Van A", age: 18 },
    { fullName: "Le Van B", age: 20 },
    { fullName: "Le Van C", age: 28 }
];
const averageAge = listUser.reduce((average, item) => average + item.age / listUser.length, 0);
console.log(averageAge); // 22
```

## Kết luận

Hàm và các phương thức mảng là nền tảng quan trọng trong JavaScript. Hãy thực hành các ví dụ trên để nắm vững kiến thức. Bạn có thể làm bài tập tại: [Link bài tập](https://dacavn.notion.site/B-i-t-p-b-i-07-Javascript-c-b-n-Ti-t3-b62c38712b4d4bdd8c4269171395f705?pvs=4).

Chúc bạn học JavaScript hiệu quả và vui vẻ!

---
