# **🎯 JavaScript**
📚 __Nội dung:__

&emsp;&emsp; [__1. Giới thiệu về ngôn ngữ lập trình JavaScript__](#1-giới-thiệu-về-ngôn-ngữ-lập-trình-javascript)

&emsp;&emsp; [__2. Variables (Biến)__](#2-variables-biến)

&emsp;&emsp; [__3. Operators (Toán tử)__](#3-operators-toán-tử)

## **1. Giới thiệu về ngôn ngữ lập trình `JavaScript`**
- __`Javascript`__ (viết tắt : JS) là một ngôn ngữ lập trình kịch bản dựa vào các đối tượng có sẵn hoặc do lập trình viên tự định nghĩa.
  
- Trước đây: được sử dụng chủ yếu để nâng cao sự tương tác của người dùng với trang web.
- Ngày nay: Sử dụng rộng rãi trong nhiều lĩnh vực.

## **2. Variables (Biến)**
### **2.1. Khái niệm**
- __Biến (variable)__ là nơi để bạn có thể lưu trữ thông tin.
- Cú pháp: __`var tenBien = giaTri;`__
  
- Trong đó:
  - tenBien: Là tên của biến các bạn muốn đặt.
  - giaTri: Là giá trị của biến, có thể là số, chuỗi, mảng, object.
- Lưu ý: Tên biến có phân biệt chữ hoa, chữ thường.
- Ví dụ:
  ```JavaScript
  var a = 15;
  var b = 20;
  var c = a + b; // Kết quả c = 35
  ```
### **2.2. Cách đặt tên cho biến**
- Quy tắc đặt tên biến:
  
  - Bắt đầu phải là chữ cái hoặc ký tự '_'
  - Không được bắt đầu bằng số (0 → 9).
  - Không được chứa ký tự đặc biệt (ví dụ: #, %, ^, -)
- Đặt tên biến ĐÚNG:
  ```JavaScript
  var tenbien = 10;
  var _tenbien = 10;
  var TenBien = 10; // PascalCase
  var ten_bien = 10; // snake_case
  var tenBien = 10; // camelCase
  ```
- Đặt tên biến SAI:
  ```JavaScript
  var 123tenbien = 10; // Sai do số đứng đầu
  var -tenbien = 10; // Sai do có ký tự
  ```

## **3. Operators (Toán tử)**
### **3.1. Arithmetic (Toán tử số học)**
- Toán tử số học là toán tử dùng để thực hiện các phép toán số học.
  
- Danh sách các toán tử số học:
  | Toán tử | Mô tả         |
  |:-------:|---------------|
  |  +      | • Phép cộng. <br> • Nếu là chuỗi thì nó sẽ thực hiện thao tác nối chuỗi. |
  |  -      | • Phép trừ.    |
  |  *      | • Phép nhân.      |
  |  **     | • Phép lũy thừa, công thức là a^b..    |
  |  /      | • Phép chia.   |
  |  %      | • Phép chia lấy phần dư.      |
  |  ++     | • Phép tăng giá trị hiện tại lên 1 đơn vị. <br> • Phép này có hai cách sử dụng đó là đặt nó trước biến (prefix - tiền tố) và đặt nó sau biến (postfix - hậu tố).      |
  |  --     | • Phép giảm giá trị hiện tại xuống 1 đơn vị. <br> • Phép này cũng có hai cách dùng đó là đặt trước biến (prefix) và đặt sau biến (postfix).      |
### **3.2. Assignment (Toán tử gán)**
- Toán tử gán dùng để gán giá trị cho một biến.

- Danh sách các toán tử gán:
  | Toán tử | Ví dụ   | Mô tả                              |
  |:-------:|:-------:|------------------------------------|
  | =       | a = b   | • Gán giá trị của biến b cho giá trị của biến. |
  | +=      | a += b  | • Tương đương với a = a + b.      |
  | -=      | a -= b  | • Tương đương với a = a - b.      |
  | *=      | a *= b  | • Tương đương với a = a * b.      |
  | /=      | a /= b  | • Tương đương với a = a / b.      |
  | %=      | a %= b  | • Tương đương với a = a % b.      |
  | **=     | a **= b | • Tương đương với a = a ** b.     |
### **3.3. Comparison (Toán tử so sánh)**
- Toán tử so sánh là toán tử hai ngôi dùng để so sánh giá trị của hai toán hạng với nhau.

- Danh sách các toán tử so sánh:
  | Toán tử | Ví dụ   | Mô tả                              |
  |:-------:|:-------:|------------------------------------|
  | >       | a > b   | • Trả về true nếu a lớn hơn b. <br> • Trả về false nếu b lớn hơn a. |
  | <       | a < b   | • Trả về true nếu a nhỏ hơn b. <br> • Trả về false nếu b nhỏ hơn a. |
  | >=      | a >= b  | • Trả về true nếu a lớn hơn hoặc bằng b. <br> • Trả về false nếu a nhỏ hơn b. |
  | <=      | a <= b  | • Trả về true nếu a nhỏ hơn hoặc bằng b. <br> • Trả về false nếu a lớn hơn b. |
  | ==      | a == b  | • Trả về true nếu a bằng b. <br> • Trả về false nếu a khác b. <br> • Không nghiêm ngặt. |
  | ===     | a === b | • Trả về true nếu giá trị của a bằng giá trị của b và a, b phải cùng kiểu dữ liệu. <br> • nghiêm ngặt. |
  | !=      | a != b  | • Trả về true nếu a khác b. <br> • Trả về false nếu a bằng b. <br> • Không nghiêm ngặt. |
  | !==     | a !== b | • Trả về true nếu giá trị của a khác giá trị của b và a, b phải khác kiểu dữ liệu. <br> • nghiêm ngặt. |
### **3.4. Logical (Toán tử logic)**
- Toán tử logic là toán tử kết nối hai hay nhiều biểu thức, dùng để kiểm tra mối quan hệ logic giữa các biểu thức.

- Kết quả cuối cùng phụ thuộc vào giá trị của từng biểu thức và loại toán tử logic.
- Danh sách các toán tử logic:
  | Toán tử | Mô tả         |
  |:-------:|---------------|
  |  &&     | • __AND__: trả về kết quả là true khi tất cả toán hạng đều true. |
  |  &#124;&#124;   | • __AND__: trả về kết quả là true khi tất cả toán hạng đều true. |
  |  !      | • __NOT__: Chuyển đổi giá trị của toán hạng từ true sang false hoặc từ false sang true. |
