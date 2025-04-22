# **🎯 JavaScript**
📚 __Nội dung:__

&emsp;&emsp; [__1. Giới thiệu về ngôn ngữ lập trình JavaScript__](#1-giới-thiệu-về-ngôn-ngữ-lập-trình-javascript)

&emsp;&emsp; [__2. Variables (Biến)__](#2-variables-biến)

&emsp;&emsp; [__3. Operators (Toán tử)__](#3-operators-toán-tử)

&emsp;&emsp; [__4. Data Types (Kiểu dữ liệu)__](#4-data-types-kiểu-dữ-liệu)

## **1. Giới thiệu về ngôn ngữ lập trình `JavaScript`**
- __`Javascript`__ (viết tắt : JS) là một ngôn ngữ lập trình kịch bản dựa vào các đối tượng có sẵn hoặc do lập trình viên tự định nghĩa.
  
- Trước đây: được sử dụng chủ yếu để nâng cao sự tương tác của người dùng với trang web.
- Ngày nay: Sử dụng rộng rãi trong nhiều lĩnh vực. Ví dụ như Web app, Mobile app, Server app, Graphic, AI,... và nhiều lĩnh vực khác

## **2. Variables (Biến)**
### **2.1. Khái niệm**
- __Biến (variable)__ là nơi để bạn có thể lưu trữ thông tin.
- Cú pháp: __`var tenBien = giaTri;`__
  
- Trong đó:
  - `tenBien`: Là tên của biến các bạn muốn đặt.
  - `giaTri`: Là giá trị của biến, có thể là số, chuỗi, mảng, object.
- Lưu ý: Tên biến có phân biệt chữ hoa, chữ thường.
- Ví dụ:
  ```JavaScript
  var a = 15;
  var b = 20;
  var c = a + b;
  console.log(c);
  
  var hoVaTen = "Nguyen Van A";
  console.log(hoVaTen);
  ```
  Output
  ```
  35
  Nguyen Van A
  ```
### **2.2. Cách đặt tên cho biến**
- Quy tắc đặt tên biến:
  
  - Bắt đầu phải là chữ cái hoặc ký tự '_'
  - Không được bắt đầu bằng số (0 → 9).
  - Không được chứa ký tự đặc biệt (ví dụ: #, %, ^, -)
- Đặt tên biến __ĐÚNG__:
  ```JavaScript
  var tenbien = 10;
  var _tenbien = 10;
  var TenBien = 10; // PascalCase
  var ten_bien = 10; // snake_case
  var tenBien = 10; // camelCase
  ```
- Đặt tên biến __SAI__:
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
- Ví dụ:
  ```JavaScript
  var a = 10;
  var b = 3;
  
  var c = a + b;
  console.log(c); // 13
  
  var c = a - b;
  console.log(c); // 7
  
  var c = a * b;
  console.log(c); // 30
  
  var c = a / b;
  console.log(c); // 3.3333333333333335
  
  var c = a % b;
  console.log(c); // 1
  
  var a = 10;
  var b = ++a;
  console.log(a); // 11
  console.log(b); // 11
  
  var a = 10;
  var b = a++;
  console.log(a); // 11
  console.log(b); // 10
  
  var a = 10;
  var b = --a;
  console.log(a); // 9
  console.log(b); // 9
  
  var a = 10;
  var b = a--;
  console.log(a); // 9
  console.log(b); // 10
  
  var a = 20;
  var b = a++ - --a + ++a; // b = 20  -  20 +  21
  console.log(b); // 21
  
  var a = 20;
  var b = a++ - a-- + --a * 3; // b = 20  - 21  +  19 * 3
  console.log(b); // 56
  
  var a = 20;
  var b = --a - ++a + --a - a++ + a-- * 2; // b =  19 -  20 +  19 - 19  + 20  * 2
  console.log(b); // 39
  ```
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
- Ví dụ:
  ```JavaScript
  var a = 10;
  var b = 20;
  b = a;
  console.log(b);
  
  var a = 10;
  var b = 3;
  b += a; // b = b + a = 10 + 3
  console.log(b); // 13
  
  var a = 3;
  var b = 10;
  b -= a; // b = b - a = 10 - 3
  console.log(b); // 7
  
  var a = 3;
  var b = 10;
  b /= a; // b = b / a = 10 / 3
  console.log(b); // 3.33333
  
  var a = 3;
  var b = 10;
  b *= a; // b = b * a = 10 * 3
  console.log(b); // 30
  
  var a = 3;
  var b = 10;
  b **= a; // b = b ** a = 10 ** 3
  console.log(b); // 1000
  
  var a = 3;
  var b = 10;
  b %= a; // b = b % a = 10 % 3
  console.log(b); // 1
  ```
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
- Ví dụ:
  ```JavaScript
  var a = 10;
  var b = 20;
  var c = a <= b;
  console.log(c); // true
  
  var a = "20";
  var b = 20;
  var c = a == b;
  console.log(c); // true
  
  var a = "20";
  var b = 20;
  var c = a === b;
  console.log(c); // false
  
  var a = "20";
  var b = 20;
  var c = a != b;
  console.log(c); // false
  
  var a = "20";
  var b = 20;
  var c = a !== b;
  console.log(c); // true
  ```
### **3.4. Logical (Toán tử logic)**
- Toán tử logic là toán tử kết nối hai hay nhiều biểu thức, dùng để kiểm tra mối quan hệ logic giữa các biểu thức.

- Kết quả cuối cùng phụ thuộc vào giá trị của từng biểu thức và loại toán tử logic.
- Danh sách các toán tử logic:
  | Toán tử | Mô tả         |
  |:-------:|---------------|
  |  &&     | • __AND__: trả về kết quả là true khi tất cả toán hạng đều true. |
  |  &#124;&#124;   | • __AND__: trả về kết quả là true khi tất cả toán hạng đều true. |
  |  !      | • __NOT__: Chuyển đổi giá trị của toán hạng từ true sang false hoặc từ false sang true. |
- Ví dụ:
  ```JavaScript
  var a = 10;
  var b = 20;
  var c = 30;
  var d = 40;
  var e = 60;
  var f = 50;
  
  var g = a < b && c < d && e < f;
  console.log(g); // false
  
  var g = a > b || c > d || e > f;
  console.log(g); // true
  
  var a = true;
  var b = !a;
  console.log(b); // false
  ```

## **4. Data Types (Kiểu dữ liệu)**
### **4.1. Kiểu dữ liệu nguyên thủy (Primitive Data)**
- Có 6 kiểu: `Number`, `String`, `Boolean`, `Undefined`, `Null`, `Symbol`.

- Kiểu `Number`:
  - Là kiểu dữ liệu dạng số.
    
  - Hai loại số là: số nguyên và số thực.
  - 3 số đặc biệt là:
    - Infinity: là số dương vô cùng.
      
    - -Infinity: là số âm vô cùng.
    - NaN: là viết tắt của Not a Number, những trường hợp tính toán sai hoặc kết quả của một phép tính không xác định.
  - Ví dụ:
    ```JavaScript
    var a = 10;
    var b = 10.5;
    var c = Infinity;
    var d = -Infinity;
    var e = 10/"abc";
    
    console.log(a);
    console.log(b);
    console.log(c);
    console.log(d);
    console.log(e); // NaN
    ```
    Output:
    ```
    10
    10.5
    Infinity
    -Infinity
    NaN
    ```
   
- Kiểu `String`:
  - Là kiểu dữ liệu dùng để biểu diễn chữ, văn bản, đoạn văn bản,...
    
  - Có 3 cách để biểu diễn string:
    - Dùng dấu nháy đơn: '
      
    - Dùng dấu nháy kép: "
    - Dùng dấu backtick: `
  - Ví dụ:
    ```JavaScript
    var fullName = 'Nguyen Van A';
    var email = "levana@gmail.com";
    var phone = `0123456789`;
    var message1 = "Xin chào " + fullName + ", email của bạn là "+ email +", sdt của bạn là: " + phone + ".";
    var message2 = `Xin chào ${fullName}, email của bạn là ${email}, sđt của bạn là: ${phone}.`;
    
    console.log(message1);
    console.log(message2);
    ```
    Output:
    ```
    Xin chào Le Van A, email của bạn là levana@gmail.com, sdt của bạn là: 0123456789.
    Xin chào Le Van A, email của bạn là levana@gmail.com, sđt của bạn là: 0123456789.
    ```

- Kiểu `Boolean`:
  - Là kiểu dữ liệu __logic__ chỉ bao gồm 2 giá trị:
    - `true` (đúng, chính xác)
      
    - `false` (sai, không chính xác)
  - Ví dụ:
    ```JavaScript
    var a = true;
    var b = false;
    
    console.log(a);
    console.log(b);
    ```
    Output:
    ```
    true
    false
    ```
   
- Kiểu `Undefined`:
  - Là kiểu dữ liệu mà khi __khai báo ra một biến__ và __không gán giá trị__ thì kết quả trả về là `undefined`.

  - Ví dụ:
    ```JavaScript
    var n;
    console.log(n);
    ```
    Output:
    ```
    undefined
    ```
 
- Kiểu `Null`:
  - Là kiểu dữ liệu đặc biệt, chỉ bao gồm một __giá trị là `null`__ (không biết giá trị, không có giá trị).

  - Ví dụ:
    ```JavaScript
    var a = null;
    console.log(a);
    ```
    Output:
    ```
    null
    ```
 
- Kiểu `Symbol`:
  - Symbol là một kiểu dữ liệu nguyên thủy dùng để tạo ra các __giá trị duy nhất (unique value)__ và __bất biến (immutable)__.
 

### **4.2. Dữ liệu phức tạp (Complex Data)**
- Có __2 kiểu__: `Function`, `Object`.

- Kiểu __`Function`__:
  - Là một chương trình con giúp thực thi một công việc cụ thể.
    
  - Cú pháp:
    ```JavaScript
    function tenHam(thamSo1, thamSo2, …) {
        // Code
    }
    ```
  - Ví dụ:
    ```JavaScript
    function St(h, a, b) {
        var S = 1/2 * h * (a + b);
        return S;
    }
    
    var h1 = 10;
    var a1 = 12;
    var b1 = 15;
    var S1 = St(h1, a1, b1);
    
    console.log(S1);
    
    var h2 = 8;
    var a2 = 9;
    var b2 = 12;
    var S2 = St(h2, a2, b2);
    
    console.log(S2);
    ```
    Output
    ```
    135
    84
    ```

- Kiểu __`Object`__:
  - Là một tập hợp gồm các cặp __key - value__ (khóa - giá trị).
    
  - value có thể là bất kỳ kiểu dữ liệu nào.
  - Có 2 loại: __`Object`__ và __`Array`__.
    
  - Loại __`Object`__:
    - Cú pháp:
      ```JavaScript
      var tenBien = {
          key1: "value 1",
          key2: "value 2",
          ...
      }
      ```
      
    - Ví dụ:
      ```JavaScript
      var infoUser = {
          fullName: "Nguyen Van A",
          email: "nguyenvana@gmail.com",
          phone: "0123456789",
          age: 18,
          status: true,
          address: null,
          socials: {
              facebook: "fb.com/nguyenvana",
              tiktok: "tiktok.com/nguyenvana",
              instagram: "instagram.com/nguyenvana"
          },
          cart: [
              {
                  title: "Sản phẩm 1",
                  quantity: 2,
                  price: 20000
              },
              {
                  title: "Sản phẩm 2",
                  quantity: 3,
                  price: 50000
              },
              {
                  title: "Sản phẩm 3",
                  quantity: 6,
                  price: 5000
              }
          ]
      };
      
      console.log(infoUser)
      console.log(infoUser.fullName)
      console.log(infoUser.socials.facebook)
      ```
      Output
      ```
      {
        fullName: 'Nguyen Van A',
        email: 'nguyenvana@gmail.com',
        phone: '0123456789',
        age: 18,
        status: true,
        address: null,
        socials: {
          facebook: 'fb.com/nguyenvana',
          tiktok: 'tiktok.com/nguyenvana',
          instagram: 'instagram.com/nguyenvana'
        },
        cart: [
          { title: 'Sản phẩm 1', quantity: 2, price: 20000 },
          { title: 'Sản phẩm 2', quantity: 3, price: 50000 },
          { title: 'Sản phẩm 3', quantity: 6, price: 5000 }
        ]
      }
      Nguyen Van A
      fb.com/nguyenvana
      ```
      
  - Loại __`Array`__:
 
    - Cú pháp:
      ```JavaScript
      var tenBien = [
          "value 1",
          "value 2",
          ...
      ]
      ```
    - Ví dụ 1:
      ```JavaScript
        var listUser = [
            "Nguyen Van A",
            "Nguyen Van B",
            "Nguyen Van C"
        ];
      
        console.log(listUser);
        console.log(listUser[0]);
        console.log(listUser[1]);
        console.log(listUser[2]);
        ```
        Output
        ```
        [ 'Nguyen Van A', 'Nguyen Van B', 'Nguyen Van C' ]
        Nguyen Van A
        Nguyen Van B
        Nguyen Van C
        ```

    - Ví dụ 2:
      ```JavaScript
        var listUser = [
            {
                fullName: "Nguyen Van A",
                email: "levana@gmail.com",
                age: 18
            },
            {
                fullName: "Nguyen Van B",
                email: "levanb@gmail.com",
                age: 20
            },
            {
                fullName: "Nguyen Van C",
                email: "levanc@gmail.com",
                age: 22
            }
        ];
      
        console.log(listUser);
        console.log(listUser[0]);
        console.log(listUser[0].fullName);
        console.log(listUser[0].email);
        console.log(listUser[0].age);
        ```
        Output
        ```
        [
          { fullName: 'Le Van A', email: 'nguyenvana@gmail.com', age: 18 },
          { fullName: 'Le Van B', email: 'nguyenvanb@gmail.com', age: 20 },
          { fullName: 'Le Van C', email: 'nguyenvanc@gmail.com', age: 22 }
        ]
        { fullName: 'Nguyen Van A', email: 'nguyenvana@gmail.com', age: 18 }
        Nguyen Van A
        nguyenvana@gmail.com
        18
        ```
