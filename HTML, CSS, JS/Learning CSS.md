### khái niệm
 - Là ngôn ngữ dùng để định dạng và trang trí giao diện trang web
 - kiểm soát các thẻ hiển thị trên trang web gồm kích thước, màu sác , khoảng cách, kiểu chữ

### Cách sử dụng inline, internal, external

**inline**
- viết mã CSS trực tiếp trong các thẻ HTML bằng thuộc tính  'style' 

	```html
	<!DOCTYPE html>  
	<html>  
	<body>  
	  
	<h1 style="color:blue;text-align:center;">This is a heading</h1>  
	<p style="color:red;">This is a paragraph.</p>  
	  
	</body>  
	</html>
	```

**internal**
- viết CSS bằng 'style' trong thẻ 'head', CSS này sẽ áp dụng cho toàn bộ tài liệu
	
	```html
			<!DOCTYPE html>  
			<html>  
			<head>  
				<style>  
					body {  background-color: linen;}  
					  h1 {  color: maroon;  margin-left: 40px;}  
				</style>  
			</head>  
				<body>  
					<h1>This is a heading</h1>  
					<p>This is a paragraph.</p>  
				</body>  
			</html>
	```

**external**
- viết CSS trong tệp riêng biệt (VD: style.css) và liên kết với HTML qua thẻ 'link' trong phần 'head'

	```css
	body {  background-color: lightblue;}  
	  
	h1 {  color: navy;  
	  margin-left: 20px;}
	```

	```html
	<!DOCTYPE html>  
	<html>  
	<head>  
	<link rel="stylesheet" href="mystyle.css">  
	</head>  
	<body>  
	  
	<h1>This is a heading</h1>  
	<p>This is a paragraph.</p>  
	  
	</body>  
	</html>
	```


# Flexbox, gridbox, position, transition, typography, animation
## I. Flex-box
### Khái niệm
- là những pattern giúp thiết kế layout dễ dàng hơn
- phân chia không gian giữa các items và kiểm soát căn chỉnh chúng
- Gồm 2 phần chính: **Flex container** *(vùng chứa cha)* và **Flex items** *(vùng chứa con)*
- Thuộc tính chính của **Flex-box** `display | flex-direction | flex-wrap | flex-flow | justified-content | align-items | align-content`

#### 1.**Display**

```html
<style>
.box {
    display: flex;
}
</style>
<div class="box">
    <div class="box-item">1</div>
    <div class="box-item">2</div>
    <div class="box-item">3</div>
</div>
```

#### 2.Flex-direction
- **flex-direction: row**  - trái sang phải
```html
<style>
.box {
    display: flex;
    flex-direction: row;
}
</style>
<div class="box">
    <div class="box-item">1</div>
    <div class="box-item">2</div>
    <div class="box-item">3</div>
</div>
```
![[a9620b86-cea6-4a9a-aa77-f8d16654a546.webp]]

- **flex-direction: row-reverse** - phải sang trái
```html
<style>
.box {
    display: flex;
    flex-direction: row-reverse;
}
</style>
<div class="box">
    <div class="box-item">1</div>
    <div class="box-item">2</div>
    <div class="box-item">3</div>
</div>
```
![[Pasted image 20230804223849.png]]

- **flex-direction: column** - trên xuống dưới
```html
<style>
.box {
    display: flex;
    flex-direction: column;
}
</style>
<div class="box">
    <div class="box-item">1</div>
    <div class="box-item">2</div>
    <div class="box-item">3</div>
</div>
```
![[ba02427d-c034-4593-b6d9-ff91201d33c0.webp]]

- **flex-direction: column-reverse** - dưới lên trên
```html
<style>
.box {
    display: flex;
    flex-direction: column-reverse;
}
</style>
<div class="box">
    <div class="box-item">1</div>
    <div class="box-item">2</div>
    <div class="box-item">3</div>
</div>
```
![[984336e9-d8f3-4b06-955e-0f54144eb5dc.webp]]

#### 3.**Flex-wrap:**  
- **Flex-wrap: nowrap** - (mặc định) không có gì thay đổi
	```html
	<style>
	.box {
	    display: flex;
	    flex-wrap: nowrap;
	}
	</style>
	<div class="box">
	    <div class="box-item">1</div>
	    <div class="box-item">2</div>
	    <div class="box-item">3</div>
	    <div class="box-item">4</div>
	    <div class="box-item">5</div>
	    <div class="box-item">6</div>
	    <div class="box-item">7</div>
	    <div class="box-item">8</div>
	    <div class="box-item">9</div>
	</div>
	```
	
	![[49300129-3f31-4e69-becc-61eb42b234f6 1.webp]]

- **Flex-wrap: wrap** - item sẽ được bao trọn trong container
![[7b855427-cdd0-423b-8336-9c513649a01e.webp]]

- **FLex-wrap: wrap-reverse** - ngược lại
![[6c2f9d35-2a1b-4500-bfa0-71028cd30a13.webp]]

#### 4.**Flex-flow:** (rút gọn của flex-direction và flex-wrap)
- `flex-flow: flex-direction | flex-wrap`
	```html
	<style>
	.box {
	  display: flex;
	  flex-flow: row-reverse wrap;
	}
	</style>
	<div class="box">
	    <div class="box-item">1</div>
	    <div class="box-item">2</div>
	    <div class="box-item">3</div>
	</div>
		```

#### 5.**Justify-content** 
VD
```html
<style>
.box {
  display: flex;
  justify-content: flex-start;
}
</style>
<div class="box">
    <div class="box-item">1</div>
    <div class="box-item">2</div>
    <div class="box-item">3</div>
    <div class="box-item">4</div>
</div>
```

- **Justify-content: flex-start** - canh lề bên trái
	![[a9620b86-cea6-4a9a-aa77-f8d16654a546.png]]  

- **Justify-content: flex-end** - canh lề phải
	![[Pasted image 20230804223849.png]]  

- **Justify-content: center** - canh giữa theo chiều ngang 
	![](https://images.viblo.asia/42059f30-a8ed-4c03-8a69-06fb2dce2333.png)  

- **justify-content: space-between** - canh lề đều nhau  
	![](https://images.viblo.asia/85000744-07a2-4e7b-994f-0893aacdde92.png)  

- **justify-content: space-around** - chia khoảng cách đầu cuối. Khoảng cách đầu cuối = 1/2 khoảng của các item
	![](https://images.viblo.asia/d9f57f2e-dbe3-4476-baf9-74e3b7e6cbff.png)  

- **justify-content: space-evenly**  - chia đều các khoảng cách của các item
	![](https://images.viblo.asia/2ded4196-e51e-4fca-b93e-065f432f64f6.png)



#### 6.**align-item**
- **align-item: stretch** - item sẽ được kéo dài so với chiều cao container 
```html
<style>
.box {
  display: flex;
  align-item: stretch;
}
</style>
<div class="box">
    <div class="box-item">1</div>
    <div class="box-item">2</div>
    <div class="box-item">3</div>
    <div class="box-item">4</div>
</div>
```
![[16d76964-a366-4215-8185-d29bbcf14ab8.png]]
- **align-item: flex-start** - canh lề bên trên
![[c67fcfc4-9a2c-4fdc-9c2b-0764e72eb338.webp]]
- **align-item: flex-end** - canh lề bên dưới
	![[c67fcfc4-9a2c-4fdc-9c2b-0764e72eb338.png]]
	
- **align-item: center** - canh giữa
	![[0ffe3809-2031-4f0f-90d2-54a69413b7c3.png]]
- **align-item: baseline** - canh giữa theo dòng văn bản
	![[481911b3-8171-41f8-bf45-41098e6e8f57.png]]


## II. Grid-box
- cho phép sắp xếp các thành phần của 1 tranh thành các vùng
```html
<div class="grid-container">
  <div class="grid-item">1</div>
  <div class="grid-item">2</div>
  <div class="grid-item">3</div>  
  <div class="grid-item">4</div>
  <div class="grid-item">5</div>
  <div class="grid-item">6</div>  
  <div class="grid-item">7</div>
  <div class="grid-item">8</div>
  <div class="grid-item">9</div>  
</div>
```
#### **Display**: grid
```css
.grid-container{
	display: grid;
}
```

- **Column** *(cột)*
	- **grid-template-columns:** - điều chỉnh theo cột
		```css
		.grid-container{
			display: grid;
			grid-template-columns: auto auto auto; //tự động cân bằng
		}
		```
		```css
		.grid-container{
			display: grid;
			grid-template-columns: 20% 30% 40%; //chỉnh theo tỷ lệ
		}
		```

- **Row** *(hàng)*
	- **grid-template-row:** - điều chỉnh theo hàng
		- điều chỉnh hàng dựa theo thuộc tính `grid-template-rows` (tương tự như cột)
- **Gaps** *(khoảng trống)*
	- **grid-gap:** - điều chỉnh khoảng trống giữa cột và hàng
		- điều chỉnh kích thước khoảng cách bằng các thuộc tính
		```css
		grid-column-gap: ; //khoảng cách theo cột
		grid-row-gap: ; //khoảng cách theo hàng
		grid-cap: ; //khoảng cách theo hàng và cột
		```

- **Lines** *(viền giữa cột và hàng)*
	- có thể tùy chỉnh gộp cột bằng cách css ở từng ô theo các thuộc tính
		```css
		grid-columns-start: ; /*Line bắt đầu*/
		grid-columns-end: ; /*Line kết thúc*/
		grid-row-start: ; /*Line bắt đầu*/
		grid-row-end: ; /*Line kết thúc*/
		```
	- Hoặc
		```css
		grid-columns: ; /*Line bắt đầu | Line kết thúc*/
		grid-row: ; /*Line bắt đầu | Line kết thúc*/
		```
	- VD:
		```html
		<div class="grid-container">
			<div class="grid-item-1">1</div>
			<div class="grid-item-2">2</div>
			<div class="grid-item-3">3</div>  
			<div class="grid-item-4">4</div>
			<div class="grid-item-5">5</div>
			<div class="grid-item-6">6</div>  
			<div class="grid-item-7">7</div>
			<div class="grid-item-8">8</div>
		</div>
		```
	
		```css
		/*gộp cột từ line 1 đến 3 */
		.grid-item-1{
			grid-column-start: 1;
			grid-column-end: 3;
		}
		/*gộp hàng từ line 1 đến 3 */
		.grid-item-2{
			grid-row-start: 1;
			grid-row-end: 3;
		}
		```


	- hoặc có thể tùy chỉnh theo vùng thuộc tính
		```css
		grid-area: grid-row-start / grid-column-start / grid-row-end / grid-column-end;
		```

# Position (absolute, relative, fixed, sticky). Kỹ thuật center element
## Position
- dùng để điều chỉnh vị trí của một phần tử trên trang web
- kiểm soát một phần tử được hiển thị và vị trí trong bố cục của trang
- các giá trị chính của 'position' `positon: relative | absolute | fixed | sticky`
	```html
	<body>
	   <div class="box-orange"></div>
	   <div class="box-blue"></div>
	</body>
	```
- #### 1. Relative (vị trí tương đối)
	- không bị phụ thuộc đối tượng nào khác
	- lấy vị trí đang đứng làm gốc tọa độ
	- dễ dàng thay đổi vị trí nhờ vào các thuộc tính `top | right | bottom | left`
		```css
		.box-orange {
		  position: relative;  /** chúng ta có thể di chuyển được element*/
		  background: orange;
		  width: 100px;
		  height: 100px;
		  top: 100px;         /*dịch chuyển xuống 100px từ vị trí ban đầu của nó */
		  left: 100px;        /* dịch chuyển sang phải 100px */
		}
		```
- #### 2.Absolute (vị trí tuyệt đối)
	- bị phụ thuộc vào thẻ cha gần nhất có thuộc tính **'position'**
	- lấy vị trí của thẻ cha làm gốc tọa độ
	- dễ dàng thay đổi vị trí nhờ vào các thuộc tính `top | right | bottom | left`
		```html
		<body>
		   <div class="container">            <!--div "container" làm thẻ cha-->
	       <div class="box-orange"></div>
	       <div class="box-blue"></div>
		   </div>
		</body>
		```
		
		```css
		.box-orange {
		  position: absolute;
		  background: orange;
		  width: 100px;
		  height: 100px;
		}
		```
	- `position: absolute` đưa element về vị trí top-left theo thẻ cha
		```css
		.container{
		  background: black;
		  position: relative;
		}
		.box-orange {
		  position: absolute;
		  background: orange;
		  width: 100px;
		  height: 100px;
		  left: 5px;
		  top: 5px;             /*di chuyển hình xuống 5px*/
		}
		```

- #### 3.Fixed
	- tương tự như `absolute`
	- phần tử phụ thuộc vào cửa sổ của trình duyệt và không thay đổi khi scroll

		*html*
		```html
		  <body>
		    <div class="container">
			  <p>Scroll down the page</p>
		      <div class="box-orange"></div>
		    </div>
		```

		*css*
		```css
		.container { 
		  position: relative;
		  background: lightgray;
		  width: 50%;
		  margin: 0 auto;
		  height: 1000px;
		}
		
		.container p {
		  text-align: center;
		  font-size: 20px;
		}
		
		.box-orange {
		  background: orange;
		  width: 100px;
		  height: 100px;
		  position: fixed;
		  right: 5px;
		}
		```

- #### 4.Sticky
	- là sự kết hợp của `position: relative` và `position: fixed`
	- có thể hiểu là khi bạn cuộn đến vị trí của element sẽ giống như là ```fixed``` và khi cuộn ra khỏi element thì giống như là ```relative```
		```html
		  <body>
		    <div class="container">
		      <div class="box-orange"></div>
		      <div class="box-blue"></div>
		      <p>Scroll down the page</p>
		    </div>
		```

		```css
			.container {
			  position: relative;
			  background: lightgray;
			  width: 50%;
			  margin: 0 auto;
			  height: 1000px;
			}
			
			.container p {
			  text-align: center;
			  font-size: 20px;
			}
			
			.box-orange {
			  background: orange;
			  width: 100px;
			  height: 100px;
			  position: sticky;
			  right: 20px;
			}
			
			.box-blue {
			  background: lightblue;
			  width: 100px;
			  height: 100px;
			}
		```
		>*note: `position: sticky` không được hỗ trợ trên nhiều trình duyệt, khuyên ko nên dùng*
		

## kỹ thuật center element
- #### 1.căn giữa bằng flex-box
	- căn giữa ngang và dọc
		```css
		.container {
		  display: flex;
		  justify-content: center; /* Căn giữa ngang */
		  align-items: center; /* Căn giữa dọc */
		}
		```
- #### 2.căn giữa bằng margin
	- áp dụng khi biết được kích thước phần tử con
		```css
			.child {
			  width: 200px; /* Kích thước của phần tử con */
			  margin: 0 auto; /* Căn giữa ngang bằng cách đặt left và right là auto */
			}
		```
- #### 3.căn giữa bằng`position: obsolute` 
	- áp dụng khi muốn căn giữa  trong một phần tử cha 
		```css
		.container {
		  position: relative; /* Đặt vị trí tương đối */
		}
		
		.child {
		  position: absolute;
		  top: 50%;
		  left: 50%;
		}
		```
- #### 4.căn giữa bằng grid
	- sử dụng `grid` căn giữa phần tử trong một lưới
		```css
		.container {
		  display: grid;
		  place-items: center; /* Căn giữa cả ngang và dọc */
		}
		
		```

# Typography(định dạng chữ)
## Khái niệm
- là khía cạnh quan trọng trong việc thiết kế web
- giúp bạn sắp xếp và định dạng văn bản trong trang web
- #### các thuộc tính quan trọng trong Typography
	```css
	{
	font-family: arial, helvatica,...;/*phông chữ*/
	font-size: 2px, 2rem, 2%,...; /*kích thước chữ*/
	font-weight: bold, normal, 100, 200,...; /*độ đậm chữ*/
	line-height: 2px, 2rem, 2%,...; /*khoảng cách dòng*/
	text-align: 2px, 2rem, 2%,...; /*khoảng cách các ký tự*/
	text-decoration: dotted, solid,...;/*trang trí văn vản như gạch chân,gạch ngang,...*/
	color: red, rgba,...; /*màu chữ*/
		}
	```

# Animation
## Khái niệm
- cho phép tạo hiệu ứng chuyển động cho các element trong trang web mà không cần phải dùng javascript hay flash
### Ví dụ về chuyển động thẳng cho một thẻ div
*html*
```html
<div class="container">
  <div class="element"></div>
</div>
```
- Một số thuộc tính
	- #### 1.**@keyframes:** dùng để thiết lập một chuyển động
	cú pháp `@keyframes name {/code/}`
	Trong đó:
	- name: là tên chuyển động
	- code: là các đoạn code cho tiến trình chuyển động. Có 2 dạng:
		- Sử dụng phần trăm từ 0% đến 100%
		- **from...to** : thiết lập giá trị từ đầu (from-tương đương với 0%) đến kết thúc (to - tương đương 10
	- **bảng tóm tắt về các hiệu ứng animation trong CSS**
		- **@keyframes**: *chỉ định code animation*
		- **animation-name** 
		- **animation-delay**: *chỉ định trì hoãn bắt đầu animation*
		- **animation-direction**: *xác định xem chiều chạy của animation sẽ như thể nào*
		- **animation-duration**: *thiết lập khoảng thời gian thực thi chuyển động*
		- **animation-fill-mode**: *thay đổi trạng thái của element trước khi bắt đầu và kết thúc*
		- **animation-iteration-count**: *thiết lập số lần thực hiện một animation*
		- **animation-play-state**: ; /**/ 
		- **animation-timing-function**: *xác định tốc độ thay đổi khi hiệu ứng di chuyển*
	- #### 2.cách sử dụng các animation
		```html
		<body>
			<div></div>
		</body>
		```
	- Thay đổi màu nền background, cú pháp from...to
		```css
		/* code animation */
		@keyframes example {  
		  from {background-color: pink;}
		  to {background-color: purple;}
		}
		/* Áp dụng animation vào phần tử */
		div {  
			width: 100px;  
			height: 100px;  
			background-color: purple;  
			animation-name: example;  
			animation-duration: 4s;
		}
		```
	- thay đổi màu nền background, cú pháp phần trăm(%)
		```css
		/* Code animation */
		@keyframes example { 
			0% {
			background-color: crimso
			} 
			25% {
			background-color: lightsalmon;
			}  
			50% {
			background-color: pink;
			}  
			100% {
			background-color: indigo;
			}
		}
		/* Áp dụng animation vào phần tử */
		div {  
			width: 100px;  
			height: 100px;  
			background-color: purple;  
			animation-name: example;  
			animation-duration: 4s;
		}
		```

	- ##### animation-delay
		- độ trễ 3s trước khi bắt đầu hiệu ứng
			```css
			/* Code animation */
			@keyframes example { 
				0% {
				background-color: crimso
				} 
				25% {
				background-color: lightsalmon;
				}  
				50% {
				background-color: pink;
				}  
				100% {
				background-color: indigo;
				}
			}
			/* Áp dụng animation vào phần tử */
			div {  
				width: 100px;  
				height: 100px;  
				background-color: purple;  
				animation-name: example;  
				animation-duration: 4s;
				animation-delay: 3s;
				/*nếu sử dụng giá trị âm, animation sẽ như đã chạy trong N giây*/
			}
			```

	- ##### animation-iteration-count
		- giá trị thường dùng: 
			- số lần 
			- **infinite**: lặp lại liên tục và vô hạn
			```css
			/* Code animation */
			@keyframes example { 
				0% {
				background-color: crimso
				} 
				25% {
				background-color: lightsalmon;
				}  
				50% {
				background-color: pink;
				}  
				100% {
				background-color: indigo;
				}
			}
			/* Áp dụng animation vào phần tử */
			div {  
				width: 100px;  
				height: 100px;  
				background-color: purple;  
				animation-name: example;  
				animation-duration: 4s;
				animation-iteration-count: 5; /*lặp lại 5 lần*/
				/* nếu sử dụng infinite, animation sẽ lặp lại liên tục */
			}
			```
	- ##### animation-direction
		- giá trị thường dùng
			- **normal**: di chuyển bình thường tiến về phía trước
			- **reverse**: di chuyển hướng ngược lại, lùi về sau
			- **alternate**: tiến về phía trước, sau đó lùi về hướng ngược lại
			- **alternate-reverse**: di chuyển hướng ngược lại rồi đổi chiều tiền về trước
		- VD: chạy theo hướng ngược lại
			```css
			/* Code animation */
			@keyframes example { 
				0% {
				background-color: crimso
				} 
				25% {
				background-color: lightsalmon;
				}  
				50% {
				background-color: pink;
				}  
				100% {
				background-color: indigo;
				}
			}
			/* Áp dụng animation vào phần tử */
			div {  
				width: 100px;  
				height: 100px;  
				background-color: purple;  
				animation-name: example;  
				animation-duration: 4s;
				animation-iteration-count: 5;
				animation-direction: reverse;
			}
			```
		- **chạy với giá trị alternate**
			```css
			/* Code animation */
			@keyframes example { 
				0% {
				background-color: crimso
				} 
				25% {
				background-color: lightsalmon;
				}  
				50% {
				background-color: pink;
				}  
				100% {
				background-color: indigo;
				}
			}
			/* Áp dụng animation vào phần tử */
			div {  
				width: 100px;  
				height: 100px;  
				background-color: purple;  
				animation-name: example;  
				animation-duration: 4s;
				animation-iteration-count: 5;
				animation-direction: alternate;
			}
			```
		- **chạy với giá trị alternate-reverse**
			```css
			/* Code animation */
			@keyframes example { 
				0% {
				background-color: crimso
				} 
				25% {
				background-color: lightsalmon;
				}  
				50% {
				background-color: pink;
				}  
				100% {
				background-color: indigo;
				}
			}
			/* Áp dụng animation vào phần tử */
			div {  
				width: 100px;  
				height: 100px;  
				background-color: purple;  
				animation-name: example;  
				animation-duration: 4s;
				animation-iteration-count: 5;
				animation-direction: alternate-reverse;
			}
			```
	- ##### animation-timing-function
		- các giá trị thường dùng
			- **ease**: tạo hiệu ứng chuyển động chậm rồi sau đó nhanh dần và kết thúc
			- **linear**: tạo hiệu ứng chuyển động từ bắt đầu đến kết thúc có tốc độ như nhau
			- **ease-in**: tạo hiệu ứng chuyển động chậm lúc bắt đầu
			- **ease-out**: tạo hiệu ứng chuyển động chậm đến kết thúc
			- **ease-in-out**: tạo hiệu ứng chuyển động chậm lúc bắt đầu đến lúc kết thúc
			- **cubic-bezier(n,n,n,n)**: xác định một hình dạng tùy chỉnh của đường thời gian
				- VD: `cubic-bezier(0.25, 0.1, 0.25, 1)`
			```html
			<!DOCTYPE html>
			<html>
			<head>
			<style>
				body{
				background-color:#e9d8f4;
				border: 1px solid black;
				position: relative;
				padding: auto;
				width: 600px;
				}
				div {
				width: 100px;  
				height: 50px;  
				background-color: #58257b;  
				color:white;
				text-align: center;  
				font-family:arial;  
				position: relative;  
				animation: mymove 5s infinite
				}
				 /* Cú pháp tiêu chuẩn */
				 #div1 {animation-timing-function: linear;}
				 #div2 {animation-timing-function: ease;}
				 #div3 {animation-timing-function: ease-in;}
				 #div4 {animation-timing-function: ease-out;}
				 #div5 {animation-timing-function: ease-in-out;}
				 /* Cú pháp tiêu chuẩn */
				 @keyframes mymove {  
					 from {
					 left: 0px;
					 }  
					 to {
					 left: 500px;
					 }
				 }
			</style>
			</head>
			<body>
				<div id="div1">linear</div><br>
				<div id="div2">ease</div><br>
				<div id="div3">ease-in</div><br>
				<div id="div4">ease-out</div><br>
				<div id="div5">ease-in-out</div>
			</body>
			</html>
			```
	- >##### animation-fill-mode
		- các giá trí thường dùng
			- **none**: giá trị mặc định, không có bất kỳ hiệu ứng nào
			- **forwards**: giữ lại trạng thái của frame cuối cùng khi animation hoàn thành
			- **backwards**: giữ lại trạng thái của frame đầu tiên khi animation bắt đầu
			- **both**: kết hợp `forwards` và `backwards`, đồng thời phần tử sẽ có trạng thái của frame đầu tiên trước khi animation bắt đầu và giữ lại trạng thái của frame cuối cùng sau khi animation hoàn thành.
			```html
			<!DOCTYPE html>
			<html>
			<head>
			<style>
				body{
				background-color:#e9d8f4;
				border: 1px solid black;
				position: relative;
				padding: auto;
				width: 600px;
				}
				div {
				width: 100px;  
				height: 50px;  
				background-color: #58257b;  
				color:white;
				text-align: center;  
				font-family:arial;  
				position: relative;
				animation-name: mymove;
				animation-duration: 5s;  
				animation-delay: 2s;  
				}
				
				 #div1 {animation-fill-mode: none;}
				 #div2 {animation-fill-mode: forwards;}
				 #div3 {animation-fill-mode: backwards}
				 #div4 {animation-fill-mode: both;}
				 /* Cú pháp tiêu chuẩn */
				 @keyframes mymove {  
					 from {
					 left: 0px;
					 background-color: purple
					 }  
					 to {
					 left: 500px; background-color: pink;
					 }
				 }
			</style>
			</head>
			<body>
				<div id="div1">none</div><br>
				<div id="div2">forwards</div><br>
				<div id="div3">backwards</div><br>
				<div id="div4">both</div><br>
			</body>
			</html>
			````

# Framework CSS: Bootstrap, Tailwind
- ## Khái niệm
	- ### Bootstrap
		- framework CSS được phát triển bởi Twitter. Cung cấp các thành phần UI và các lớp CSS được thiết kế sẵn để xây dựng giao diện web nhanh chóng và dễ dàng
		- Các thành phần UI bao gồm nút, biểu đồ, modals, thanh điều hướng, hình ảnh và nhiều hơn nữa
		- Bootstrap cung cấp một lưới **(grid system)** linh hoạt giúp bạn tạo cấu trúc bố cục của trang web
		- hỗ trợ **responsive** design, giúp giao diện phản hồi tốt trên nhiều kích thước màn hình
	- ### Tailwind
		- Tailwind CSS là một framework CSS utility-first. Cung cấp một tập hợp các lớp CSS nhỏ để bạn có thể tạo giao diện bằng cách kết hợp chúng lại
		- Thay vì cung cấp các thành phần sẵn có như Bootstrap, Tailwind cho phép bạn tạo các thành phần tùy chỉnh theo ý muốn bằng cách kết hợp các lớp.
		- Cung cấp một số lượng lớn các lớp CSS có thể sử dụng để điều chỉnh **typography, màu sắc, bố cục, padding, margin** và nhiều thuộc tính khác.
		- hỗ trợ **responsive** design, giúp giao diện phản hồi tốt trên nhiều kích thước màn hình
- ## cách sử dụng
	- ### bootstrap
		- Thêm bootstrap vào **css** hay **javascript** bằng các dòng sau vào trước thẻ `head`  trong HTML
			```html
			<head>
				<!-- thêm vào css -->
			<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-4bw+/aepP/YC94hEpVNVgiZdgIC5+VKNBQNGCHeKRQN+PtmoHDEXuppvnDJzQIu9" crossorigin="anonymous"> 
				<!-- thêm vào javascript -->
				<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/js/bootstrap.bundle.min.js" integrity="sha384-HwwvtgBNo3bZJJLYd8oVXjrBZt8cqVSpeBNS5n7C8IVInixGAoxmnlMuBnhbgrkm" crossorigin="anonymous"></script>
			</head>
			```
		- Sử dụng các tiện ích css *(cơ bản)* trong bootstrap
			- **1.lưới** *(grid system)* 
				- bootstrap sử dụng lưới 12 cột giúp xây dựng bố cục linh hoạt và responsive
					```html
					<div class="container">
						<div class="row">
							<div class="col-md-6">Nội dung cột 1</div>
							<div class="col-md-6">Nội dung cột 2</div>
						</div>
					</div>
					```
			- **2.Button** *(nút)*
				- Cung cấp các lớp để tạo nút với nhiều kiểu dáng và màu sắc.
				```html
				<div class="container">
					<div class="row">
						<button class="btn btn-primary">Primary Button</button>
						<button class="btn btn-secondary">Secondary Button</button>
					</div>
				</div>
				```
			- **3.Typography** *(Kiểu chữ)*
				- Các lớp để tùy chỉnh kiểu chữ, kích thước và màu sắc.
					```html
					<div class="container">
						<div class="row">
							<h1 class="display-4">Tiêu đề lớn</h1>
							<p class="lead">Đoạn mô tả lớn và nổi bật.</p>
						</div>
					</div>
					```
			- **4.Colors** *(Màu sắc)*
				- Các lớp để định dạng màu sắc chữ, nền, biên và nhiều phần tử khác.
					```html
					<div class="container">
						<div class="row">
							<div class="text-primary">Chữ màu chính</div>
							<div class="bg-success">Nền màu thành công</div>
						</div>
					</div>
					```
			- **5.Spacing** *(Khoảng cách)*
				- Các lớp để kiểm soát margin và padding của phần tử.
					```html
					<div class="container">
						<div class="row">
							<div class="mt-3">Khoảng cách trên</div>
							<div class="p-4">Khoảng cách padding</div>
						</div>
					</div>
					```
			- **6.Alerts** *(Thông báo)*
				- Các lớp để tạo thông báo với các kiểu thành công, cảnh báo, lỗi và thông tin.
					```html
					<div class="container">
						<div class="row">
							<div class="alert alert-success">Thành công!</div>
							<div class="alert alert-warning">Cảnh báo!</div>
						</div>
					</div>
					```
			- **Forms** *(Biểu mẫu)*
				- Các lớp để tạo biểu mẫu với các kiểu input, nút và mục chọn.
					```html
					<div class="container">
						<div class="row">
							<form>
							  <input class="form-control" type="text" placeholder="Nhập thông tin">
							  <button class="btn btn-primary">Gửi</button>
							</form>
						</div>
					</div>
					```


	- ### Tailwind
		- **Cài đặt tailwind**
			- muốn cài đặt tailwind chúng ta bắt buộc cần phải tải **node.js** vào máy trước
			- cái đặt tailwind css qua **npm** bằng cách chạy câu lệnh sau
				- `mpn install tailwindcss`
		- **tạo tệp cấu hình**
			- sau khi cài đặt, cần tạo cấu hình có tailwind bằng cách chạy câu lệnh sau
				- `npx tailwindcss init`
				-  tệp cấu hình **`tailwind.config.js`** sẽ được tạo ra
		- **tích hợp với css**
			- Tạo một tệp CSS và nhập Tailwind CSS vào bằng cách thêm các dòng sau vào tệp CSS
				```css
				@import 'tailwindcss/base'; 
				@import 'tailwindcss/components'; 
				@import 'tailwindcss/utilities';
				```
			- >Đảm bảo rằng tệp CSS này được liên kết với trang HTML của bạn.
		- **Sử dụng các lớp CSS**
			- **1. Margin và Padding:**
				- `m-{size}`: margin (ngoại vi).
				- `p-{size}`: padding (khoảng cách bên trong).
				- Các giá trị `{size}: 0, 1, 2, 3, 4, 5, 6, 8, 10, 12, 16, 20, 24, 32, 40, 48, 56, 64, auto.`
					```html
					<div class="container">
						<div class="row">
							<div class="m-4">Margin 4</div>
							<div class="p-2">Padding 2</div>
						</div>
					</div>
					```
			- **2. Width và Height:**
				- `w-{size}`: width (chiều rộng).
				- `h-{size}`: height (chiều cao).
				- Các giá trị `{size}: 0, 1, 2, 3, 4, 5, 6, 8, 10, 12, 16, 20, 24, 32, 40, 48, 56, 64, auto, px, full.`
					```html
					<div class="container">
						<div class="row">
							<div class="m-4">Margin 4</div>
							<div class="p-2">Padding 2</div>
						</div>
					</div>
					```
			- **3. Background và Text Color:**
				- `bg-{color}`: background color.
				- `text-{color}`: text color.
				-  Các giá trị `{color}: gray, red, blue, green, yellow, indigo, purple, pink.` và nhiều màu khác.
					```html
					<div class="container">
						<div class="row">
							<div class="bg-green-300 text-white">Background Green, Text White</div>
						</div>
					</div>
					```
			- **4. Typography:**
				- `text-{size}`: kích thước chữ.
				- `font-{family}`: kiểu font chữ.
				- `font-{weight}`: độ đậm nhẹ của font.
				- Các giá trị `{size}`: `xs`, `sm`, `base`, `lg`, `xl`, `2xl`, `3xl`, `4xl`, `5xl`, `6xl`, `7xl`, `8xl`, `9xl`.
				- Các giá trị `{family}`: `sans`, `serif`, `mono`.
					```html
					<div class="container">
						<div class="row">
							<h2 class="text-3xl font-bold">Header 2 with Large Font</h2>
							<p class="text-gray-600">Gray Text</p>
						</div>
					</div>
					```
			- **5. Display và Flexbox:**
				- `block`: Hiển thị kiểu block.
				- `inline-block`: Hiển thị kiểu inline block.
				- `flex`: Hiển thị kiểu flex.
				- `justify-{alignment}`: Canh chỉnh các phần tử con theo chiều ngang.
				- `items-{alignment}`: Canh chỉnh các phần tử con theo chiều dọc.
					```html
					<div class="container">
						<div class="row">
							<div class="flex justify-center items-center h-24 bg-indigo-200">
							  <span>Centered Content</span>
							</div>
						</div>
					</div>
					```
			- **6. Border và Radius:**
				- `border`: Hiển thị đường viền.
				- `border-{width}`: Độ dày đường viền.
				- `rounded`: Bo tròn các góc.
				- `rounded-{size}`: Độ cong các góc.
				- Các giá trị `{size}`: `none`, `sm`, `md`, `lg`, `full`.
					```html
					<div class="container">
						<div class="row">
							<div class="border rounded-lg p-3">Border with Rounded Corners</div>
						</div>
					</div>
					```
			- **7. Positioning:**
				- `absolute`: Vị trí tuyệt đối.
				- `relative`: Vị trí tương đối.
				- `fixed`: Vị trí cố định.
				- `top-{size}`: Canh chỉnh phía trên.
				- `right-{size}`: Canh chỉnh phía bên phải.
					```html
					<div class="container">
						<div class="row">
							<div class="relative">
							  <div class="absolute top-0 right-0 bg-red-400">Top Right</div>
							</div>
						</div>
					</div>
					```
			- **8. Hover và Focus:**
				- `hover:bg-{color}`: Background color khi hover.
				- `focus:outline-none`: Loại bỏ viền khi focus.
					```html
					<div class="container">
						<div class="row">
							<button class="bg-blue-500 hover:bg-blue-700 focus:outline-none text-white py-2 px-4">
							  Hover and Focus Effect
							</button>
						</div>
					</div>
					```

