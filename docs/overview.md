# Databases Management

## 1. What is Database (DB) ?
  
DB (cơ sở dữ liệu), là `một nhóm/tập hợp các dữ liệu có cấu trúc` để dễ dàng truy cập và quản lý.

DB tồn tại dưới dạng `tập tin` hoặc có thể được lưu trữ trên thiết bị có chức năng ghi nhớ như: 
thẻ nhớ, đĩa cứng, CD...

Một Database thường được quản lý bởi một `Database Management System` (hệ quản trị cơ sở dữ liệu).

Chức năng chính của Database là: lưu trữ, truy xuất và cập nhật dữ liệu...

Một số loại của DB (hoặc Hệ quản trị cơ sở dữ liệu):
  
  * Relational databases (Cơ sở dữ liệu quan hệ)
  
  * Distributed databases (Cơ sở dữ liệu phân tán)
  
  * Graph databases (Cơ sở dữ liệu biểu đồ)
  
  * ...

*Reference:*

https://topdev.vn/blog/database-la-gi-cac-kieu-database-pho-bien-va-ung-dung/ <br>
https://www.oracle.com/database/what-is-database/ <br>
https://www.javatpoint.com/what-is-database

## 2. Basic concepts in Relational databases
* **Table**

Trong `Relational databases`  Table dùng để `lưu trữ dữ liệu`. Nó sẽ `chứa các dữ liệu liên quan` của một đối tượng mà đó thể hiện dưới dạng `row`, `column`.

Ví dụ table tên NhanVien chứa thông tin về nhân viên trong một công ty.

*Reference:*

https://giasutinhoc.vn/database/sqlserver-2014/tao-table-trong-sql-server-2014-bai-3-2/
https://www.javatpoint.com/what-is-rdbms
https://xuanthulab.net/cac-khai-niem-co-ban-va-thuc-hanh-tao-cac-bang-table-trong-ms-access.html

* **Field (Column)**

Field là `trường dữ liệu `(hoặc một cột trong bảng) chứa thông tin cụ thể của một thuộc tính của đối tượng.

Ví dụ table NhanVien sẽ gồm các field/cột như là ID, Tên, Tuổi, Địa chỉ...

Field gồm `Field Name` (tên cột) và `Field Value` (dữ liệu của cột).

*Reference:*

https://www.javatpoint.com/what-is-rdbms <br>
https://teachcomputerscience.com/database-record/ <br>
https://study.com/academy/lesson/database-fields-definition-types.html

* **Record (Row)**

Một hàng trong bảng được gọi là `Record`, nó chứa một nhóm các dữ liệu hoặc `tập hợp dữ liệu của các field`.

* **Relationships**

Thể hiện sự liên kết dữ các bảng/đối tượng với nhau.

Các loại của Database Relationships:

`One to One`:  

Mối quan hệ 1-1, một đối tượng A tương ứng với một thực thể B và ngược lại

Ví dự: Một người chỉ có một chứng minh nhân dân và một CMND chỉ đại diện cho 1 người.

`One to Many`

Mối quan hệ 1-nhiều, một đối tượng A tương ứng với nhiều đối tượng B và một đối tượng B chỉ tương ứng với một đối tượng A:

Ví dụ: Một lớp có nhiều học sinh nhưng một học sinh chỉ thuộc về một lớp.
 
`Many to Many`: 
 
Mối quan hệ nhiều-nhiều, một đối tượng A tương ứng với nhiều đối tượng B và ngược lại.

Ví dụ: Một môn học sẽ có nhiều sinh viên đăng ký học và mỗi sinh viên có thể đang ký nhiều môn khác nhau.

*Reference:*

https://giasutinhoc.vn/database/co-so-du-lieu/mo-hinh-du-lieu-quan-he-bai-3-2/ <br>
https://mybule.wordpress.com/2016/11/15/sql-cach-xay-dung-database-va-moi-quan-he-giua-cac-thuc-the-cua-mang-xa-ho-facebook-user-post-comment-postcategory/ <br>
https://www.slideshare.net/tuoitrecomvn/slide-02-23857249

* **Primary key and Foreign Key** (Khoá chính và khoá ngoại)

`Primary key`

Khóa chính (hay ràng buộc khóa chính) được sử dụng để định danh duy nhất mỗi record trong table của cơ sở dữ liệu.

Dữ liệu (value) của field khóa chính phải có tính duy nhất. 

Mỗi table nên chỉ có một khóa chính, khóa chính có thể tạo ra từ nhiều field của table.

Ngoài ra, nó còn dùng để thiết lập quan hệ (hay ràng buộc tham chiếu) giữa hai table trong cơ sở dữ liệu.

`Foreign Key`

Khóa ngoại của một table được xem như con trỏ trỏ tới khóa chính của table khác.

*Reference:*
https://viblo.asia/p/khac-biet-giua-khoa-chinh-va-khoa-ngoai-trong-sql-924lJMdWZPM

## 3. Databases Design (Thiết kế cơ sở dữ liệu)
Mục đích của thiết kế cơ sở dữ liệu:

* Tiết kiệm bộ nhớ lưu trữ bằng cách hạn chế những dữ liệu trùng lặp.

* Duy trì dữ liệu chính xác và toàn vẹn.(Toàn vẹn dữ liệu là *dữ liệu không bị thay đổi, mất trong khi lưu trữ hoặc truyền tải*)

* Giúp truy xuất dữ liệu hiệu quả hơn.

Các bước để thiết kế Database:

* Phân tích yêu cầu

* Thiết kế Database, gồm 2 mô hình dữ liệu (data model)
	
	* `Logical Model`: Thiết kế Database trên giấy hoặc qua các lược đồ (ERD - Entity Relationship Dỉagram). Thiết kế này không dựa vào *Hệ quản trị Dữ liệu* nào 

	* `Physical Model`: Thiết kế Database dựa vào Logical Model để phù hợp với một *Hệ quản trị Dữ liệu* cụ thể.

* Thực hiện

`Normalization` (Chuẩn hoá) một mô hình dữ liệu khi thiết kế cần tuân theo một số các quy tắc để giúp hạn chế dư thừa và toàn vẹn của dữ liệu.

*Reference:*

https://www.lucidchart.com/pages/database-diagram/database-design <br>
https://www.sqlshack.com/what-is-database-normalization-in-sql-server/ <br>
https://www.javatpoint.com/database-design

## 4. Concepts
### Data Analysis

Data analysis (phân tích dữ liệu) liên quan tới quá trình chọn lọc dữ liệu và tìm kiếm, thu thập những thông tin quan trọng thông qua một số lượng rất lớn các thông tin hỗn độn.

Những dữ liệu chắt lọc hay còn được gọi là `key insight` này có giá trị rất lớn với các công ty ở mọi quy mô trong việc đưa ra các quyết định có tầm ảnh hưởng.

### Data Science
Là một nghiên cứu đề cập đến việc xác định, trình bày và trích xuất các thông tin có ý nghĩa từ các nguồn dữ liệu, được sử dụng cho mục đích kinh doanh.

Với số lượng dữ liệu khổng lồ được tạo ra mỗi phút, yêu cầu trích xuất thông tin chi tiết hữu ích là điều bắt buộc đối với các doanh nghiệp, giúp họ tìm ra điểm nổi bật trong thị trường rộng lớn.

Một Data Scientist (Nhà khoa học dữ liệu) không chỉ dừng lại ở việc phân tích dữ liệu, mà còn biết sử dụng thuật toán `Machine Learning` để dự đoán tương lai của một sự kiện.

**Data Science ở cấp độ cao hơn Data Analysis, Data Science thiên về lập trình, xây dựng các thuật toán hay tạo ra các mô hình dự báo.**

*Reference:*

https://insight.isb.edu.vn/data-science-la-gi/ <br>
https://nordiccoder.com/blog/lo-trinh-tro-thanh-data-scientist-nordic-coder/ <br>
https://itviec.com/blog/data-scientist-la-gi/
https://nordiccoder.com/blog/data-analysis-la-gi-hoc-data-analysis-o-dau/

### Big Data
Những dữ liệu đáp ứng được **3V** sau có thể được xem là `Big Data`:

* `Volume`: Tức là Khối lượng – Dung lượng, big data phải là một tập dữ liệu đủ lớn, chưa có móc cụ thể để đánh giá độ lớn của nó.

* `Variety`: Tức là sự đa dạng, big data là những dữ liệu không giới hạn sự đa dạng. Nó bao gồm tất cả các loại dữ liệu trên đời như: hình ảnh, text, video, âm thanh,… bất kể dữ liệu đó là có cấu trúc, bán cấu trúc, hay không có cấu trúc.

* `Velocity`: Tức là độ gia tăng của dữ liệu, dữ liệu của big data được tăng lên theo thời gian, và sự tăng lên này là cực kỳ lớn. Và cũng như tiêu chí về `Volume`, không có một tiêu chuẩn nào để đánh giá sự gia tăng thế nào là lớn.

`Big Data` thường để phân tích chỉ số, nhu cầu thị trường, dự doán xu hướng, phát triển AI...

*Reference:*
https://topdev.vn/blog/big-data/ <br>
https://phambinh.net/bai-viet/bigdata-la-gi-no-khac-gi-voi-data-thuong/

### Các loại dữ liệu
* `Structured Data/ Dữ liệu có cấu trúc`

Đây là loại dữ liệu dễ dàng tìm kiếm và sắp xếp nhất, vì nó thường được hàm chứa trong các cột và hàng, và các thành phần của chúng có thể được liên kết bằng những trường được định sẵn từ trước. 

Ví dụ những dữ liệu bạn có thể lưu trữ trong một tệp Excel và chúng ta sẽ thấy ngay được. Dữ liệu có cấu trúc bao gồm dữ liệu tài chính như các giao dịch, chi tiết địa chỉ, thông tin nhân khẩu, đánh giá của người dùng, các bản ghi chú của máy, dữ liệu địa điểm từ các thiết bị thông minh, …

Thông thường, dữ liệu có cấu trúc được quản lý bằng Ngôn ngữ `Truy vấn Có cấu trúc` (Structured Query Language — SQL) - một loại ngôn ngữ lập trình được phát triển bởi IBM từ những năm 1970..

* `Non-Structured Data/ Dữ liệu không cấu trúc`

Một phần rất lớn của tất cả dữ liệu trên thế giới này là dữ liệu Không cấu trúc. Loại dữ liệu này là loại không thể chứa trong CSDL dạng hàng và cột, và nó cũng không có mô hình dữ liệu nào liên quan. 

Ví dụ như một đoạn chữ trong một email chẳng hạn. Sự thiếu hụt về cấu trúc đã khiến dữ liệu Không cấu trúc trở nên khó tìm kiếm, quản lý và phân tích.

Các ví dụ khác của dữ liệu Không cấu trúc gồm có hình ảnh, phim và các tệp âm thanh, các tệp chứa chữ cái, các nội dung từ mạng xã hội, hình ảnh từ vệ tinh, các bài thuyết trình, tệp PDF, các câu trả lời từ bản khảo sát câu hỏi mở, các trang web và bản thu từ các cuộc gọi hỗ trợ khách hàng.

* `Semi-Structured Data/ Dữ liệu bán cấu trúc`

Loại dữ liệu này có một số tính chất đồng nhất có thể xác định được, nhưng lại không hình thành một cấu trúc rõ ràng và phù hợp với CSDL quan hệ.

Email là một ví dụ điển hình. Nội dung thực chất của email thuộc dạng Không cấu trúc, nhưng nó lại mang các dữ liệu Có cấu trúc như tên, địa chỉ của người gửi và người nhận, thời gian gửi, … Một ví dụ khác là ảnh kỹ thuật số. Bản thân hình ảnh đó là Không cấu trúc, nhưng nếu bức ảnh đó được chụp từ điện thoại, thì nó sẽ được gắn ngày tháng và thời gian, nhãn về địa lý, và có khi còn có ID của thiết bị. Một khi được lưu trữ, bức ảnh đó cũng có thể được gắn nhãn như ‘chó’ hay ‘mèo’.

*Reference:*

https://unitrain.edu.vn/su-khac-biet-giua-du-lieu-co-cau-truc-ban-cau-truc-va-khong-cau-truc/ <br>
https://vietmoz.net/du-lieu-co-cau-truc-structured-data/ <br>
https://filegi.com/tech-term/semi-structured-data-8214/

**Update soon...**
<hr>
Networking and Internet
	Basic Concepts
		Domain
		Host
		Port
		IP Address
		Protocol
		MAC Address
		Client-Server Model
	DNS Server
	Socket
	Perfomance
		Bandwidth
		Delay
	Devices
		Router
		Hub
		Bride
		Wireless Router
		Switch
	Network Topology
		Start Topology
		Bus Topology
		Mesh Topology
		Ring Topology
		Daisy chain Topology
	History
		Web 1.0
		Web 2.0

Computer Organization and Architecture
	Machine code
	Assembler language
	Registers, instruction address, heap, stack

Programming
	Basic Concepts
		Data Type
		Variables
		Arithmetic
			Math operators (add, subtract, multiply, divide, modulo)
			Logic operators (And, Or, Negate)
		Syntax
		Control Structures
			Conditional(If...else, switch...case)
			Loop
				For loops
				While loops
				Do...While loops
		Functions
	Intermediate Concepts
		Data Structures
		Algorithms
		Programming Paradigms
			Imperative programming paradigm
				Procedural programming paradigm
				Object oriented programming (OOP)
				Parallel processing approach
			 Declarative programming paradigm
				Logic programming paradigms 
				Functional programming paradigms
				Database/Data driven programming
		Concern
		Coupling / Cohesion
		Implementation
		Modeling
	Advanced Conceps
		Design Pattern
		Framework

Development
	Concepts
		Clean code
		Re-use code
		Module
		Hard code
		Bug/ Fix Bug
		Maintenance
		Open Source
		Frameworks
		Libraries
		Platforms
		CMS
		Requirements
	Design
		UI/UX
		Prototype
	Testing
		Code Coverages
		Unit Test
	Deloy
		Automatic
		Munual
	Release
	Software Development Models
		Waterfall
		V-model (Validation and Verification model)
		Scrum
	Childs
		Web Development
			Font-End
			Back-End
		Software Development
		Mobile Development

Cloud Computing

Information Security

Artificial Intelligence (AI)
	Machine Learning
	Neural Network
	Robotics
	Expert Systems
	Fuzzy Logic
	Natural Language Processing

Game Design

Multimedia Design
	Audio/Video Edit
	Graphic Design (2D/3D)
	Special effects
	Installation artist

Technical Support

Other
	SEO
	Content Writer
	Digital Marketing
