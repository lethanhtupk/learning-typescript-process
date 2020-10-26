
## Data Types

### Cách khai báo data types:

* Cấu trúc khai báo data types là *:<type>*
* Cách khai báo type cho tham số
  ```Javascript
  function sayHi(humanNam: string) {}
  ```
* Có thể khai báo kiểu dữ liệu trả về của function 
  ```Javascript
  function concatString(str1: string, str2: string): string { }
  ```
* Syntaxt này cũng sử dụng cho khai báo biến
  ```Javascript
  let a: string = "Hello";
  ```
 
 ### Các kiểu dữ liệu hỗ trợ 
 
 * String 
 * Number 
 * Boolean
 * Any
 Không xác định rõ kiểu dữ liệu cho các biến có khai báo kiểu dữ liệu any 
 * Array
 Nếu không xác định rõ kiểu dữ liệu cho thành phần trong array, array sẽ lấy kiểu dữ liệu của giá trị được khởi tạo. Nếu khai báo một array rỗng, vậy kiểu giữ liệu trong array là **any**
 ```Javascript 
 const pets: string[] = ["Cho", "Meo"]
 ```
 Trong trường hợp bạn muốn khai báo một array có chữa nhiều kiểu dữ liệu, sử dụng any
 ```Javascript
 const pets: any[] = ["cho", "meo"]
 ```
 * Tuples 
 * Enums
 * Function 
 Typescript cho phép bạn define funtion type. Ví dụ sau khai báo một biến tham chiếu đến một function với một signature (thứ tự tham số) cụ thệ
 ```Javascript 
 let myMathFunction: (num1: number, num2: number) => string;
 ```
 Bây giờ, *myMathFunction* chỉ có thể gán với giá trị là một function với 2 tham số có kiểu là number 
 * Objects 
 Cách khai báo một object trong typescript như sau:
 ```Javascript
 let person: {
  firstName: string, lastName: string, age: number
  } = {firstName: "Tu", lastName: "Le", age: "22"}
  ```
 
