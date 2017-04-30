
### Cấu trúc Website cơ bản
> tham khảo ở [Website Skeleton](https://github.com/easywebhub/easymarket/blob/master/README.md)

> 2 phần chính của websites là `Layout` và `Content`

- Layout: (`/layout/*.html`) là giao diện cho từng trang của website
   - mỗi trang website phải thuộc 1 layout cụ thể
   - những phần dùng chung giữa các layouts được gọi là Partial (`/layout/partial/*.html`)
   - có thêm Category layouts (`/layout/default.category.html`) và Tags layouts để làm giao diện riêng cho các trang Categories hoặc Tags
   - chứa `html, css, js` code nên phù hợp với lập trình viên

- Content: chứa thông tin của websites gồm 2 loại: Page và Meta
   - Page: (`/content/*.md`) thông tin thuộc 1 trang cụ thể
   - Meta: (`/content/metadata/*.json`) thông tin chung có thể sử dụng ở nhiều trang hoặc trên tất cả các trang của websites
   - để điều chỉnh, thay đổi nội dung trên web, người dùng sử dụng Công cụ nhập liệu (dạng Form, Inline Editor) đơn giản

- Lưu ý: Những phần cho phép điều chỉnh phải nằm trên `Content`, không được nằm ở `Layout` 


### OnePage Website
> Là trang website chỉ có 1 trang duy nhất, website giới thiệu đơn giản, trang landingpage 

- vẫn có menu nhưng các phần trong menu vẫn nằm trên chính trang đó
- không cần sử dụng Partial layouts như footer, header, ... vì chỉ có 1 layout

- Binding dữ liệu giữa Content và Layout : [expressions](http://handlebarsjs.com/expressions.html)

### SinglePage Website 
> gồm nhiều trang, mỗi trang có 1 layout riêng

- có phần  dùng chung giữa các trang này
   - footer, header, ... nằm trong các Partial layouts tương ứng
   - Tham khảo Partial của handlebar [partials](http://handlebarsjs.com/partials.html)
   

- dữ liệu dùng chung nằm 
   - trong Global Meta `/metadata/global.json` 
   - nếu phức tạp thì nằm trong Meta riêng `/metadata/file-name.json`
   - cú pháp binding:  `{{meta-file-name.field-path}}`, ví dụ `{{global.title}}` 

### MultiplePage Website
> nhiều trang sử dụng chung 1 layout, như trang bài viết chi tiết, trang sản phẩm chi tiết, ...

- Các trang dùng chung 1 layout sẽ được tóm lượt trong trang Danh mục (Category Page) và được sắp xếp theo thứ tự: mới cập nhật, ...

- Trường hợp trang Danh mục có nhiều trang chi tiết, thì sẽ cần Phân Trang (Pagination) thành từng page 

- Các trang chi tiết có thể được phân chia theo nhiều chủ đề (Tags) khác nhau của trang web

- Các trang có cùng chung 1 chủ đề, sẽ thuộc trang Chủ đề (Tags Page) riêng và được sắp xếp theo thứ tự, cũng như được Phân Trang tương tự trang Danh Mục (Category)

- Các trang Danh Muc, hoặc Chủ đề có thể có giao diện riêng, bằng cách sử dụng Category, Tags Layouts tương ứng.

