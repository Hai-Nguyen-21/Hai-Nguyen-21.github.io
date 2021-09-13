


**Default Method**

- Như chúng ta đã biết từ java 7 đổ xuống thì trong các method trong interface chỉ được phép miêu tả (**declaration**) mà không được phép định nghĩa nó (**definition**). Nhưng đối với java 8 thì có thêm 2 khái niệm mới về interface đó là **default method** và **static method**.

Trong bài viết lần này, tôi sẽ chỉ giới thiệu về **default method** thôi nhé.

1. **Default Method- Phương pháp mặc định**:

**1.1  Cách viết:**  

`	`Public interface DAO{

`	`default void log(String mss){

`		`System.out.println(“hi “ + mss);

} 

}

\+ Tại đó chúng ta có thể viết, định nghĩa method đó.

\+ Khi 1 lớp interface extends lớp interface đó có 3 lựa chọn

1. Có thể không override default method đó
1. Có thể override rồi viết lại định nghĩa cho nó
1. Có thể đổi từ default method sang abstract

\+  Nếu một abstract class/concrete class implements từ interface IDBManager trên thì chỉ có 2 sự lựa chọn:

1. Nếu không làm gì với method log(message) thì method log() sẽ được thừa kế từ interface.
1. Có thể overriden lại method log(message) nhưng method phải ở dạng abstract hoặc bình thường (không có default method cho class) 
   - Ví dụ:

*public abstract class AbstractDBManager  implements IDBManager{*

`	`*public abstract void log(String message);*

*}*

*public class BearDBManager implements IDBManager{*

`	`*public void log(String message){*

`    	`*System.out.println("BEAR: " + message);*

`    `*}*

*}*

**1.2  Mục đích**

Giả sử trong quá trình phát triển, người ta muốn bổ sung 1 method vào interface là search(message) cho phép tìm kiếm thông tin sinh viên , như vậy như ở phiên bản java 7, nếu thêm 1 method vào interface thì bắt buộc phải sửa chữa tất cả các concrete classes implement từ interface đó, cụ thể ở đây là ta phải implement method search (message) .

VD:

![](Aspose.Words.6467a2d1-a00d-4d09-aee7-3cd182444978.001.jpeg)

nay với java 8 muốn thêm vào 1 method trong interface ta chỉ việc đặt từ khoá default vào như sau:

public interface IDBManager{

`					`//------------------------

`    		        `public default void Search(String message){

`    					`//----------------------------------------

`    				`}

}

tất cả các classes implements từ **DAOsv** sẽ được kế thừa method Search (message) và chúng ta không phải sửa chữa lại các classes đó. Mục đích của default method ra đời là để bổ sung thêm các method vào interface mà không phải thay đổi những implementation code trước đây (đảm bảo tính tương thích).

3. **Lợi ích:**
1. Trong quá trình phát triển, người ta muốn thêm 1 vài method nữa vào trong lớp interface. Nếu như ở các java trước thì khi thêm 1 method vào interface thì toàn bộ những lớp nào implements interface đó đều cần phải override method đó nữa -> gây ra nhiều sự bất tiện
1. Còn ở trong java 8 thì chúng ta chỉ cần để method đó thành dạng default method là done :v. Class nào cần dùng thì override còn không thì không cũng được
1. Một trong những tiện ích lớn nhất của default method đó là: Sử dụng trong việc dùng Comparator với Comparator.comparing() và Comparator.thenComparing()

\+ Ví dụ: ở những java phiên bản trước thì phải 

![](Aspose.Words.6467a2d1-a00d-4d09-aee7-3cd182444978.002.png)

\+ Còn ở java 8 thì tiện lợi hơn nhiều:

![](Aspose.Words.6467a2d1-a00d-4d09-aee7-3cd182444978.003.png)













3. **Một số lưu ý khi sử dụng default method:**

\+ Khi 1 class implement 2 interface khác nhau và 2 interface đấy có tên giống nhau thì compiler của java sẽ báo lỗi , vì nó không xác định được default method nào sẽ được chọn trong nhiều default method giống khai báo.

\+ Nếu chúng ta overriden 1 method của java.lang.Object ví dụ như equals, trình biên dịch sẽ thông báo cho chúng ta 1 error "A default method cannot override a method from java.lang.Object", Java 8 không cho phép override method của Object dưới dạng default method.
