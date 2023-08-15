## Khái niệm
- npm và Yarn là hai công cụ của quản lý gói (package manager) được sử dụng rộng rãi trong môi trường phát triển JavaScript để quản lý các thư viện, gói mã nguồn mở và các tài nguyên khác được sử dụng trong dự án.
- ### NPM (Node Package Manager)
	- Là công cụ quản lý gói chính cho Node.js và được tích hợp sẵn khi bạn cài đặt Node.js. npm cho phép bạn tải về và cài đặt các gói thư viện JavaScript từ kho lưu trữ npm (npm registry). Bạn có thể quản lý các gói cục bộ hoặc toàn cầu và tạo ra tệp package.json để xác định các phụ thuộc và cấu hình cho dự án.
- ### Yarn 
	- Yarn cũng là một công cụ quản lý gói cho Node.js, được phát triển bởi Facebook. Yarn có mục tiêu cung cấp khả năng quản lý gói hiệu quả và tải gói nhanh hơn bằng cách sử dụng cơ chế cache. Nó sử dụng file yarn.lock để đảm bảo tính nhất quán trong việc quản lý phụ thuộc.

## Cách sử dụng npm và yarn
### NPM
1. **NPM** được cài đặt với **Node.js**, Điều này có nghĩa là bạn phải cài đặt Node.js để cài đặt npm trên máy tính của mình.Tải xuống Node.js từ trang web chính thức của [Node.js]([https://nodejs.org](https://nodejs.org/)).
	- Khi bạn tải **NodeJS** về máy thì đã có sẵn **npm** rồi. Tuy nhiên,để kiểm tra xem trên hệ thống của bạn NPM đã được cài đặt chưa thì bạn sẽ dụng lệnh `npm -v`. Trong trường hợp có một phiên bản hiện ra thì có nghĩa là hệ thống của bạn đã được cài đặt NPM.
2. Bạn có thể sử dụng npm để cài đặt các thư viện  Javascript bằng cách mở cửa sổ terminal (hoặc CMD) và thực hiện các lệnh sau:
```
npm install package-name
```
- Ví dụ bạn muốn tải Vuejs về để sử dụng thì bạn sẽ dùng lệnh:
```
npm install vue
```
- Hoặc khi muốn sử dụng Vue.js bạn chỉ cần sử dụng lệnh require():
```
var Vue = require(‘vue’);
```
### Yarn
1. **Cài đặt Yarn**:
	- Nếu bạn chưa có Yarn, bạn có thể tải từ [https://classic.yarnpkg.com/en/docs/install/](https://classic.yarnpkg.com/en/docs/install/) 
	- Sau khi cài đặt xong, bạn có thể kiểm tra phiên bản bằng cách mở terminal và chạy câu lệnh sau 
```
yarn -v
```
2. Bạn có thể sử dụng Yarn để cài đặt các thư viện  Javascript bằng cách mở cửa sổ terminal (hoặc CMD) và thực hiện các lệnh sau:
```
yarn add package-name
```
- thay thế gói package-name bằng gói bạn muốn cài đặt. Ví dụ như bạn muốn cài đặt gói lodash
```
yarn add lodash
```
- Hoặc có thể sử dụng có thể sử dụng lệnh require() để cài đặt:
```
const _ = require('lodash');
```
