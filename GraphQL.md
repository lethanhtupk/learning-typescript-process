
## GraphQL

### Vấn đề với REST API 

Vấn đề đối với REST API là rest api luôn trả về một cấu trúc dữ liệu cố định tương ứng với một endpoint cố định.
Trong nhiều trường hợp, developer bắt buộc phải gọi cùng lúc nhiều API để có thể lấy được data họ cần. Nhưng tệ 
hơn có thể lấy dư luôn data mà vẫn phải gọi nhiều API. 

Ví dụ trong một server backend có các API như sau: 
* ```domain.com/authors```: Trả về toàn bộ các tác giả có trong DB bao gồm tên, id các cuốn sách đã ra mắt (1)
* ```domain.com/books```  : Trả về toàn bộ data sách trong DB, bao gồm tên, id tác giả, nhà xuất bản,... (2)
* ```domain.com/authors/:id```: Trả về thông tin tác giả tương ứng với id nhận được (3)
* ```domain.com/books/:id```: Trả về thông tin sách và id tác giả (4)

Giả sử ta cần lấy data về một cuốn sách có id cho sẵn kèm theo thông tin tác giả của cuốn sách đó, 
kèm theo các cuốn sách mà tác giả này sáng tác (nhưng lần này chỉ cần tên sách). vậy ta cần gọi nhưng API nào? 
Ta cần phải gọi API thứ 4 một lần, sau đó lấy id tác giả gọi API thứ 3 một lần, sau đó với mỗi id của cuốn sách 
nhận được thì gọi tiếp API 4 => Quá nhiều API mà lại thừa dữ liệu cần dùng 

#### GraphQL sinh ra để giải quyết vấn đề này.

### Appllo Client 

Apollo client là một library giúp tạo và gửi query từ client đến server để nhận về dữ liệu. (Tương tự axios)

### Tạo query graphQL trong React app như thế nào? 

GraphQL query không phải Javascript, nên ta phải xử dụng thêm một library là ```gql``` để giúp react có thể hiểu được query language
và sau đó nhận được data từ query trả về. 
