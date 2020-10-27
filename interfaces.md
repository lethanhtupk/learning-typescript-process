## Interfaces 

* Cách định nghĩa một interface:
```Javascript 
interface IPerson {
  firstName: string;
  }
```
Tên của interface hoàn toàn do người dùng định nghĩa, nhưng nên bắt đầu bằng **I** để biết rõ đây là interface khi ta nhìn vào code. 

### Type keyword and interface 

Sự khác biết giữa type và interface là không rõ ràng, nhưng giữa chúng có sự khác biệt về khả năng xử dụng 
* interface có thể merge còn type thì không 
```Javascript 
interface Song {
  artistName: string;
}
interface Song {
  songName: string
}
const song: Song {
  artisName: "Tran Lap",
  songName: "blablabla"
}
```
* interface có thể extends và implements, type thì không 
Interface có thể extends class và ta cũng có thể viết class để implements interface trong typescript 
* Intersection
Intersection cho phép ta kết hợp nhiều type thành một type duy nhất, Sử dụng **&** keyword để thực hiện 
```Javascript
type Name = {
  name: “string”
};

type Age = {
  age: number
};

type Person = Name & Age;
```
Ta cũng có thể kết hợp 2 interface thành một type trong typescript. Ngược lại thì không được
```Javascript 
interface Name {
  name: “string”
};

interface Age {
  age: number
};

type Person = Name & Age;
```
* Unions 
Union type cho phép ta tạo ra một type mới có thể có chứa giá trị của một hoặc một vài type. Để tạo một union type, sử dụng **|** keyword 
```Javascript 
type Man = {
  name: “string”
};

type Woman = {
  name: “string”
};

type Person = Man | Woman;
```
Tương tự như intersection, ta có thể tạo một union type bằng cách kết hợp 2 interfaces, nhưng ngược lại thì không được 
```Javascript 
interface Man {
  name: "string"
};

interface Woman {
  name: "string"
};

type Person = Man | Woman;
```
* Tuples 
Trong Typescript, ta chỉ có thể định nghĩa một tuples thông qua sử dụng type, không thể sử dụng interface
```Javascript 
type Reponse = [string, number]
```
Nhưng ta vẫn có thể sử dụng tuple trong một interface 
```Javascript 
interface Response {
  value: [string, number]
}
```

### Nên sử dụng type hay interface 

Việc sử dụng type hay interface là tùy hoàn cảnh. 

Interface tốt hơn trong việc bạn cần phải định nghĩa mới một object hoặc method của một object. Ví dụ, trong ứng dụng react, khi bạn cần định nghĩa một props mà một component sẽ được nhận, tốt nhất là sử dụng interface 
```Javascript 
interface TodoProps {
  name: string;
  isCompleted: boolean
};

const Todo: React.FC<TodoProps> = ({ name, isCompleted }) => {
  ...
};
```
Type sử dụng khi bạn cần tạo một function. Ví dụ, tưởng tượng rằng bạn đang có một function sẽ trả về 1 object, trường hợp này thì nên sử dụng type 
```Javascript 
type Person = {
  name: string,
  age: number
};

type ReturnPerson = (
  person: Person
) => Person;

const returnPerson: ReturnPerson = (person) => {
  return person;
};
```
Tóm lại interface thường sử dụng với object và method object trong khi type tốt hơn được sử dụng với function, complex type, etc....
