**Lambda Expression- Tính năng thú vị của Java 8**

1. **Định nghĩa**

\- Là một hàm không có tên (**anonymous function**) với các tham số (**parameters**) và nội dung thực thi (**body**). 


\- Nội dung thực thi của Lambda expression có thể là một khối lệnh hoặc một biểu thức.


\- Dấu “->” tách biệt các tham số và nội dung thực thi.

1. **Cú pháp**

(argument-list) -> {body}


\+ Argument-list : danh sách tham số, có thể không có, có một hoặc nhiều tham số.
\+ Arrow-operator: toán tử mũi tiên được sử dụng để liên kết danh sách tham số và body của biểu thức.
\+ Body: nội dung thực thi, là 1 khối lệnh hoặc 1 biểu thức.

1. **Ví dụ**

() -> "Hello"  Không có tham số và trả về một chuỗi

(double x) -> x + 1 Có một tham số x và trả về giá trị tham số tăng lên 1

(int x, int y) -> x + y Có 2 tham số kiểu int và trả về tổng

1. **Một số quy tắc trong Lambda Expression**
1. Có thể bỏ qua kiểu dữ liệu của parameter truyền vào

(String msg) -> {System.out.println (msg);} 
=>   (msg) -> {System.out.println (msg);} 

1. Nếu không có parameter ,bỏ dấu () trống

() -> {System.out.println (“Hello”);} 


1. Nếu chỉ có 1 parameter, có thể bỏ luôn dấu ()

(double x) -> x + 1 
=>   x -> x+1

1. Nếu anonymous function chỉ có 1 câu lệnh , có thể bỏ dấu {}

`   `(msg) -> {System.out.println (msg);} 
=>    msg -> System.out.println (msg); 

1. Nếu chỉ return 1 giá trị , có thể bỏ chữ return 

x -> return x + 1 
=>    x -> x + 1 

1. **Ứng dụng**
   1. **Duyệt List**
      1. **Cách 1 – for i**

for (int i = 0; i < listNV.size(); i++) {

`            `listNV.get(i).xuat();

` `}

1. **Cách 2 – for each**

for(NhanVien x:listNV){

`            `x.xuat();

}

1. **Cách 3 – biểu thức Lambda**

listNV.forEach(x -> {

`            `x.xuat();

`        `});




1. **Sắp xếp chuỗi**
   1. **Cách cũ**

public void sortByName() {

Comparator<Staff>  com = new Comparator< Staff >() {

`            `@Override

`            `public int compare(Staff o1, Staff o2) {

`                `return o1.getName ().compareTo(o2.getName ());

`            `}

`        `};

`        `listNV.sort(com);

`        `System.out.println("DSNV sắp theo họ tên là:");

`           `xuatDSNV();

`    	`}

1. **Cách 1 – dùng Lambda theo Collections**

public void sortByName () {

`        		`Collections.sort(listNV, (Staff o1, Staff o2)

`                `-> {

`            `return o1.getName ().compareToIgnoreCase(o2.getName ());

`       	 `});

`        	`System.out.println("DSNV sắp theo họ tên là:");

`        		`xuatDSNV();

`    	`}

1. **Cách 2 – cũng là Collections nhưng ngắn hơn 😊)**

public void sortByName () {

`        		`listNV.sort((o1, o2)-> {

`            		`return o1.getName ().compareTo(o2.getName ());

`        		`});

`        `System.out.println("DSNV sắp theo họ tên là:");

`        `xuatDSNV();


