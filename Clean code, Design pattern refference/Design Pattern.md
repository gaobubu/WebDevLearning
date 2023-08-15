# Signleton
## Khái niệm 
- **Signleton** được sử dụng để đảm bảo rằng một lớp chỉ có duy nhất một thể hiện (instance) và cung cấp một điểm truy cập toàn cục đến instance.
- Mẫu thiết kế **Singleton** thường được sử dụng khi bạn muốn đảm bảo rằng có một thể hiện duy nhất của một lớp và muốn tránh việc tạo ra nhiều thể hiện không cần thiết.
- Cách để triển khai **Signleton** trong Javascript
```js
function User() {  
  // do we have an existing instance?
  if (typeof User.instance === 'object') {
      return User.instance;
  }

  // proceed as normal
  this.firstName = 'John';
  this.lastName = 'Doe';

  // cache
  User.instance = this;

  // implicit return
  // return this;
}

// Usage:
var curUser = new User();
console.log(curUser.firstName, curUser.lastName); // John Doe

var other = new User();
console.log(other.firstName, other.lastName);     // John Doe
console.log(other === curUser);                   // true
```
- Trong ví dụ trên:
	- khi khởi tạo **curUser** (lần đầu tiên), User.instance đang có giá trị là undefined, nên mọi thứ được xử lý như bình thường. Khi kết thúc hàm, ta gán **User.instance = this** hay nói cách khác là **User.instance = curUser**. Đến khi khởi tạo đối tượng thứ hai là other, lúc này User.instance đã là curUser - một object, nên hàm trên sẽ return về User.instance (curUser). Đó, dù có gọi hàm khởi tạo bao nhiêu lần thì ta cũng chỉ thu được một đối tượng duy nhất.
# Solid
 - **SOLID** là một tập hợp các nguyên tắc thiết kế phần mềm quan trọng để tạo ra mã nguồn dễ bảo trì, mở rộng và thay đổi. SOLID là viết tắt của năm nguyên tắc: 
	 1. **Single Responsibility Principle (SRP)**-nguyên tắc đơn trách nhiệm: Một lớp nên chỉ có một trách nhiệm duy nhất và nên chỉ thay đổi vì một lý do duy nhất. Điều này giúp tách biệt các phần khác nhau của mã và tăng tính rõ ràng trong thiết kế.
	 2. **Open/Closed Principle (OCP)**-nguyên tắc mở đóng: Mã nguồn nên được mở rộng để thêm tính năng mới mà không cần sửa đổi mã hiện có. Điều này giúp giảm nguy cơ gây lỗi khi thay đổi mã cũ và tạo sự linh hoạt cho việc mở rộng
	 3. **Liskov Substitution Principle (LSP)**-nguyên tắc thay thế: Các đối tượng của một lớp con nên có thể thay thế cho đối tượng của lớp cha mà không làm thay đổi tính đúng đắn của chương trình. Điều này đảm bảo tính nhất quán trong hệ thống và tránh các lỗi không mong muốn khi sử dụng đa hình.
	 4. **Interface Segregation Principle (ISP)**-nguyên tắc chia giao diện: Nên tách các giao diện lớn thành các giao diện nhỏ, cụ thể để các lớp chỉ cần triển khai những phần của giao diện mà chúng thực sự cần. Điều này giảm sự phụ thuộc không cần thiết và tạo ra các giao diện nhỏ gọn và dễ quản lý.
	 5. **Dependency Inversion Principle (DIP)**-nguyên tắc đảo ngược sự phụ thuộc: Các module cấp cao không nên phụ thuộc vào các module cấp thấp, cả hai nên phụ thuộc vào các abstraction. Hơn nữa, abstraction không nên phụ thuộc vào chi tiết, mà ngược lại. Điều này thúc đẩy việc sử dụng giao diện hoặc abstract class để giảm sự ràng buộc và dễ dàng thay đổi mã.
- Ví dụ:
```js
// Single Responsibility Principle (SRP)
class Logger {
    log(message) {
        console.log(message);
    }
}
class Singleton {
    constructor() {
        if (!Singleton.instance) {
            Singleton.instance = this;
            this.logger = new Logger();
        }
        return Singleton.instance;
    }

    someMethod() {
        this.logger.log("Singleton method called");
    }
}

// Open/Closed Principle (OCP)
class SingletonExtended extends Singleton {
    anotherMethod() {
        this.logger.log("Extended Singleton method called");
    }
}

// Liskov Substitution Principle (LSP)
function useSingleton(singletonInstance) {
    singletonInstance.someMethod();
}

// Interface Segregation Principle (ISP)
class Performer {
    perform() {}
}
class Singer extends Performer {
    perform() {
        this.logger.log("Singer singing");
    }
}
class Dancer extends Performer {
    perform() {
        this.logger.log("Dancer dancing");
    }
}

// Dependency Inversion Principle (DIP)
class App {
    constructor(performer) {
        this.performer = performer;
    }
    run() {
        this.performer.perform();
    }
}

const singerApp = new App(new Singer());
singerApp.run();
const dancerApp = new App(new Dancer());
dancerApp.run();
```
- trong ví dụ trên, ta có đã triển khai môi nguyên tắc SOLID trong mốt số ví dụ cụ thể
	- **SRP**: Chia thành hai lớp **`Logger`** và **`Singleton`** để mỗi lớp có một trách nhiệm cụ thể.
	- **OCP**: Mở rộng lớp **`Singleton`** thành **`SingletonExtended`** mà không cần sửa đổi mã nguồn ban đầu.
	- **LSP**: Sử dụng hàm **`useSingleton`** để thể hiện việc đa hình và sự thay thế cho đối tượng.
	- **ISP**: Tách thành các lớp **`Singer`** và **`Dancer`** để đảm bảo các lớp con chỉ phải triển khai những phương thức liên quan đến nhiệm vụ của chúng.
	- **DIP**: Xây dựng lớp **`App`** dựa trên giao diện **`Performer`** để phụ thuộc vào một giao diện chung thay vì một lớp cụ thể.