# Design Pattern
- là mẫu (partern) để giải quyết khi gặp vấn đề
- Do người có kinh nghiệm đi trước rút ra được
- Giúp tổ chức code tốt hơn, dùng ngôn ngữ nào cũng được
# Singleton
## Khái niệm 
- **Singleton** có thể hiểu là khi bạn muốn tạo 1 object trong hệ thống mà không muốn tạo nhiều lần. Ví dụ như bạn có 1 object chứa các thiết lập hệ thống nên tạo 1 lần vì khi tạo có thể object đọc dữ liệu ở nhiều chỗ làm mất thời gian
- Cách để triển khai **Signleton** trong Javascript
```js
const Singleton = (function() {
  let instance;

  function createInstance() {
    // Khởi tạo thể hiện của Singleton ở đây
    return {
      // ...
    };
  }

  return {
    getInstance: function() {
      if (!instance) {
        instance = createInstance();
      }
      return instance;
    }
  };
})();

// Sử dụng Singleton
const instance1 = Singleton.getInstance();
const instance2 = Singleton.getInstance();

console.log(instance1 === instance2); // true, vì cả hai đều trỏ đến cùng một thể hiện
```
- Trong ví dụ trên:
	- Trong ví dụ trên, chúng ta sử dụng một hàm IIFE (Immediately Invoked Function Expression) để tạo một biến `instance` và một hàm `createInstance` để khởi tạo thể hiện của Singleton. Hàm `getInstance` kiểm tra xem đã có thể hiện nào chưa, và nếu chưa, nó sẽ tạo một thể hiện mới bằng cách gọi hàm `createInstance`.
# SOLID
 - **SOLID** là một tập hợp các nguyên tắc thiết kế phần mềm quan trọng để tạo ra mã nguồn dễ bảo trì, mở rộng và thay đổi. SOLID là viết tắt của năm nguyên tắc: 
	 1. **Single Responsibility Principle (SRP)**-nguyên tắc đơn trách nhiệm: Một class nên chỉ có một trách nhiệm duy nhất và nên chỉ thay đổi vì một lý do duy nhất. Điều này giúp tách biệt các phần khác nhau như function hay các object của code và tăng tính rõ ràng trong thiết kế.
		- Ví dụ đoạn code này
			```java
			class DealProcessor
			  def initialize(deals)
			    @deals = deals
			  end
			
			  def process
			    @deals.each do |deal|
			      Commission.create(deal: deal, amount: calculate_commission)
			      mark_deal_processed
			    end
			  end
			
			  private
			
			  def mark_deal_processed
			    @deal.processed = true
			    @deal.save!
			  end
			
			  def calculate_commission
			    @deal.dollar_amount * 0.05
			  end
			end
			```
		- Class này ngoài việc đánh dấu giao dịch đã được xử lý, còn thực hiện tính hoa hồng cho mỗi giao dịch. Sau này còn có thể thêm chức năng khác thì dẫn đến việc class này làm nhiều hơn 1 nhiệm vụ . Có thể refactor như sau:
			```java
			class DealProcessor
			  def initialize(deals)
			    @deals = deals
			  end
			
			  def process
			    @deals.each do |deal|
			      mark_deal_processed
			      CommissionCalculator.new.create_commission(deal)
			    end
			  end
			
			  private
			
			  def mark_deal_processed
			    @deal.processed = true
			    @deal.save!
			  end
			end
			
			class CommissionCalculator
			  def create_commission(deal)
			    Commission.create(deal: deal, amount: deal.dollar_amount * 0.05)
			  end
			end
			```
		- Giờ thì ta có 2 class nhỏ thực hiện 2 nhiệm vụ riêng biệt. Một processor chịu trách nhiệm lưu việc xử lý và một processor thực hiện việc tính toán.
	 1. **Open/Closed Principle (OCP)**-nguyên tắc mở đóng: Có thể thoải mái mở rộng 1 class nhưng không được sửa đổi bên trong class đó . Điều này giúp giảm nguy cơ gây lỗi khi thay đổi mã cũ và tạo sự linh hoạt cho việc mở rộng.
		- Ví dụ: 
			```java
			class Report
			  def body
			     generate_reporty_stuff
			  end
			
			  def print
			     body.to_json
			  end
			end
			```
		- Đoạn code trên đã vi phạm OCP, nếu ta muốn thay đổi định dạng của report được print ra, ta sẽ cần phải sửa đổi code của class. Refactor lại như sau:
			```java
			class Report
			  def body
			     generate_reporty_stuff
			  end
			
			  def print(formatter: JSONFormatter.new)
			     formatter.format body
			  end
			end
			```
		- Làm theo cách này thì ta vừa mở rộng tính năng mà khi thay đổi format sẽ không cần phải thay đổi code
	 1. **Liskov Substitution Principle (LSP)**-nguyên tắc thay thế: Các đối tượng của một class con  có thể thay thế cho đối tượng của class cha mà không làm thay đổi tính đúng đắn của chương trình. Điều này đảm bảo tính nhất quán trong hệ thống và tránh các lỗi không mong muốn khi sử dụng đa hình.
		- Ví dụ:
			```java
			class Rectangle
			  def set_height(height)
			    @height = height
			  end
			
			  def set_width(width)
			    @width = width
			  end
			end
			
			class Square < Rectangle
			  def set_height(height)
			    super(height)
			    @width = height
			  end
			
			  def set_width(width)
			    super(width)
			    @height = width
			  end
			end
			```
		- Hình vuông (`Square`) là con của hình chữ nhật (`Rectangle`),  class `Rectangle` có các phương thức để đặt chiều cao và chiều rộng của hình chữ nhật.  `Square` kế thừa từ `Rectangle` và ghi đè lên các phương thức để đảm bảo rằng cả chiều rộng và chiều cao đều giống nhau, hiệu quả làm cho cạnh của hình vuông bằng nhau.
	 1. **Interface Segregation Principle (ISP)**-nguyên tắc chia giao diện: Nên tách các interface lớn thành các interface nhỏ cụ thể để các class chỉ cần triển khai những phần của interface mà chúng thực sự cần. Điều này giảm sự phụ thuộc không cần thiết và tạo ra các giao diện nhỏ gọn và dễ quản lý.
		- Ví dụ
			```java
			class Car
			  def open
			  end
			
			  def start_engine
			  end
			
			   def change_engine
			   end
			end
			
			class Driver
			  def drive
			    @car.open
			    @car.start_engine
			  end
			end
			
			class Mechanic
			  def do_stuff
			    @car.change_engine
			  end
			end
			```
		- Trong đoạn code trên, class `Car` có một interface được sử riêng rẽ bởi cả `Driver` và `Mechanic`. Ta có thể refactor lại code như sau:
			```java
			class Car
			  def open
			  end
			
			  def start_engine
			  end
			end
			
			class CarInternals
			   def change_engine
			   end
			end
			
			class Driver
			  def drive
			    @car.open
			    @car.start_engine
			  end
			end
			
			class Mechanic
			  def do_stuff
			    @car_internals.change_engine
			  end
			end
			```
	 1. **Dependency Inversion Principle (DIP)**-nguyên tắc đảo ngược sự phụ thuộc: Các module cấp cao không nên phụ thuộc vào các module cấp thấp, cả hai nên phụ thuộc vào các abstraction. Hơn nữa, abstraction không nên phụ thuộc vào chi tiết, mà ngược lại. Điều này thúc đẩy việc sử dụng giao diện hoặc abstract class để giảm sự ràng buộc và dễ dàng thay đổi mã.
		- Ví dụ, lấy đoạn code OCP và thay đổi 1 chút
		```java
		class Report
		  def body
		    generate_reporty_stuff
		  end
		  
		  def print
		    JSONFormatter.new.format body
		  end
		end
		
		class JSONFormatter
		  def format body
		    ...
		  end
		end
		```
	- Chúng ta có một class thực hiện đinh dạng in ra báo cáo. Tuy nhiên code trong method print của class Report vẫn đang được fix cứng, từ đó sẽ tạo nên sự phụ thuộc của class này vào class JSONFormatter. Vì report là class trừu tượng ở mức cao hơn so với JSONFormatter.
		```java
		class Report
		  def body
		    generate_reporty_stuff
		  end
		  
		  def print formatter: JSONFormatter.new
		    formatter.format body
		  end
		end
		```
	- Sau khi được refactor, class Report đã không phụ thuộc vào class JSONFormatter và có thể sử dụng bất kỳ định dạng nào mà có định nghĩa method format.