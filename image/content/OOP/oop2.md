Tiếp nối bài viết trước, chúng ta dừng lại ở tính chất thứ nhất, hôm nay tôi sẽ giới thiệu tiếp cho các bạn 3 tính chất còn lại của lập trình hướng đối tượng nhé.

2. **Tâm pháp tầng thứ hai : Encapsulation**

Nghe đến đây chắc hẳn các bạn cũng đã mường tượng ra tính chất này nói về cái gì rồi đúng không? Và nội dung của tính chất này được hiểu như sau:

“Tính đóng gói là một cơ chế liên kết dữ liệu và code chung với nhau thành một đơn vị duy nhất. Nó cũng được hiểu với mục đích che giấu dữ liệu của bạn để đảm bảo toàn vẹn dữ liệu từ những chỉnh sửa bên ngoài.”

Vậy tức là sao?

Nhưng trước khi vào thực hành ta nên đi qua chút lý thuyết nhé. Tính đóng gói có 4 kiểu phạm vi truy cập (Access Modifier) như sau:

- **Default** (mặc định) : Nếu như bạn không khai báo phạm vi truy cập thì Java sẽ hiểu mặc định phạm vi truy cập là default. Với default thì trong lớp (class) đó và trong gói (package) đó mới có thể nhìn thấy được.
- **Private** (riêng tư) : Nếu như bạn khai báo phạm vi truy cập là private thì chỉ có thể sử dụng ở ngay trong chính lớp đó thôi.
- **Public** (công khai) : Nếu như bạn khai báo ở dạng public thì mọi thông tin trong lớp đó đều có thể được nhìn thấy từ các lớp (class), các gói (package), hay là class con (subclass)
- **Protected** (được bảo vệ) : Nếu bạn khai báo ở dạng này thì lớp (class) đó, gói (package) đó, lớp con (subclass) đó đều có thể thấy được.

**NOTE:** Có thể nhiều bạn sẽ hiểu lầm về public và protected nhưng phạm vi của pubic nó rất rộng, bạn có thể truy cập vào 1 class với các thuộc tính được public từ package này sang package khác, còn protected thì không, nó chỉ hoạt động trong chính package của nó mà thôi.

Để dễ hiểu thì các bạn có thể xem ví dụ ở dưới đây

Có phải từ những ví dụ trên mình đều lấy ví dụ cho các bạn như thế này đúng không:

![https://lh3.googleusercontent.com/mViFo3lQJ8h21t9RJn-5McE8TvRCgteUVicjG663i89p-Xf\_E0ljbMnYNimeXhZwaILwLR8-TqUOzsPw2orXkZ5cG5vr4KYiMF0iO-cu-Qfqcg8wvrwVIpwLGeShogQtNcjdT5qP](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.001.jpeg)









![https://lh4.googleusercontent.com/baQZfnjE2eTqPF4dP7eVnvjO3hSp7jVVyCermvyWddsDSWbljH-XVOCfS4RjucYzt8UJsg5CxmnsOGh0EKvzy4\_YOQn0LZGD1c3Yo3H6xPz4fR6Oruum0ZA8EKX3TgMbt6vuxKcS](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.002.jpeg)










Code ở trên cơ bản là không sai, nó vẫn chạy và diễn ra bình thường, tuy nhiên không ai mong muốn một ngày đẹp trời bạn vào xem sản phẩm của mình và bị thay đổi dữ liệu tùm lum đúng không. Để giải quyết vấn đề đó cho nên ta cần phải private hết dữ liệu lại để tránh bị sửa code từ những tác nhân bên ngoài. 

“Ơ nhưng private rồi thì sao có thể truy cập được từ các class khác?” 

Chính vì thế nên Java mới có thêm 2 phương thức thần kỳ đó chính là Getter và Setter, hai phương thức này chuyên dùng để có thể Lấy và Ghi dữ liệu. 

![https://lh4.googleusercontent.com/D1F5PJlIx4qBIk850bVXWP7R5LagQzwAOyqnj6V1Vg\_2J7eVfJqXJEcA-ZHnGMUNlweAR9HjXMC8GGRYzxNy1c3fTjg1hnoS7BKof2fsTRC6xQhJyuYuQJRUNgb5r\_gjMHKlINaE](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.003.jpeg)

![https://lh5.googleusercontent.com/XyiBoExSUXCHglUNVHJ-wRfMCPeJ-Ebsw4wk6lM86RGjxvLnbzteryau8NkkHF77\_I7sJwhf\_cexOijQxJVA7lBobot6wOeltuS7iRY695lOV9kVHhrFTZY41PAy1SH5mlfMII3t](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.004.jpeg)

Như vậy từ lần sau, chúng ta nên khai báo một lớp với những phạm vi truy cập ở dạng private để có thể bảo toàn dữ liệu và truy cập tới chúng thông qua phương thức Get và Set.

Nhìn qua một lượt ví dụ trên có bạn nào thắc mắc về dòng code này không?

![https://lh3.googleusercontent.com/Oey-KaPQ4rn5\_VyLJsWBGznSxoDpZC908e7HRWfY9TZMdr7eggUJH1eIu1vp\_IVfUksuSXUXxptywGlr8\_M9ghPtwSPNeYLDRdeIwZ\_FsQrDDOrTl3PDFfvh0CgoWBu9h-NSv0hr](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.005.jpeg)

Đây được gọi là Constructor không tham số, Constructor này sẽ luôn được mặc định gọi ra kể cả khi bạn có khai báo hay không. Ngoài Constructor không tham số ta cũng có Constructor có tham số, riêng Constructor có tham số thì bắt buộc bạn phải khai báo. Constructor có tham số có nhiệm vụ giống với Get và Set, bạn có thể truyền dữ liệu vào đó mà không cần Get và Set.

![https://lh6.googleusercontent.com/I9E1X0pvVpd0X4e6ADZf9bA5fvt\_nt0DwERkDsOLJfkHBw0ik6-CbuKniL1O2-n1lDfwt-gfPGkXC-ildjp8wNgS1dVgkuLly\_sG4-ll7Sf4b6S3LeSZjtBhHwxk1F1BGwkb1GG7](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.006.jpeg)![https://lh4.googleusercontent.com/N0U3IcavntsCub5IsS-ZMqPWKqKzWpUW-j-ZkwN3gyy7scIbfZ8nWGEQ9CtoBhjYjP1FHPgcKwxkG484Jj8yv9xxUP6aLN0TI\_Xddi81ewHXVeULljPjZbf3uDu5LmeztoVxi8\_F](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.007.jpeg)![https://lh5.googleusercontent.com/qardQLOrItqjwWx0\_LuHYNwzlmkv0NiDX-hDehKE\_82H5T86BkZCLBVc8N1ebVscrOCbxzxMhZMN6FsgszyKDvja9RNvYNbp6gCv4D-gSIIw75UBf197\_KkqmFmzI2PVPL8yRxKl](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.008.jpeg)

Như vậy là các bạn đã hiểu về tính chất thứ 2 trong OOP rồi, tiếp theo ta sẽ đến với tính chất thứ 3 đó là **tính trừu tượng**.

3. **Tâm pháp tầng thứ ba : Abstraction**

Vậy trừu tượng nghĩa là sao? 

Theo mình thì trừu tượng cũng như một tảng băng chìm vậy, ta chỉ có thể nhìn được những bề nổi và nhận ra nó sẽ làm gì còn bề dưới tảng băng ta không hề hay biết nó to hay nhỏ, kích thước ra sao.

Vậy từ đây mình có thể giải thích ngắn gọn về tính chất này như sau:



“Tính trừu tượng là một tiến trình ẩn các chi tiết trình triển khai và chỉ hiển thị tính năng tới người dùng. Tính trừu tượng cho phép bạn loại bỏ tính chất phức tạp của đối tượng bằng cách chỉ đưa ra các thuộc tính và phương thức cần thiết của đối tượng trong lập trình.”

Có hai cách để ta có thể triển khai được tính trừu tượng:

- Sử dụng Abstract Class
- Sử dụng Interface

`			`**3.1. Abstract Class**

Một lớp được khai báo với từ khóa abstract tức là một lớp abstract. Lúc này bạn sẽ không thể sử dụng từ khóa “new”, có nghĩa là bạn không thể tạo instance từ một lớp trừu tượng. Cách duy nhất đó là dùng một lớp con kế thừa lại lớp abstract class. 

Để dễ hiểu mình có ví dụ như sau:

![https://lh3.googleusercontent.com/9zGWc-aURHtzoKXTejLeG0oY2jB0T7BABKU\_1M68-RjOsvwt\_sQl8Bq4yuJveLCSepZlyCpRbLboURgExAEQ8n9dBGpos05xqYnz9g2lIVbIG1r5j8UB7XSH06pxHnoG9gRh5s2-](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.009.jpeg)










![https://lh3.googleusercontent.com/vQldKbEvJEs4XnF3uhipAg2mT0MLD-P-SihblELzOh4zPNGtq0-6Pe0FYAyqfnFZEdzVSi92Lmkt7XuC6HfZOOPL3B-oy0I4iC48yw9d\_q7ERPt9-KOCVAM3mRG51DXjz7OVCrxa](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.010.jpeg)













Bên trên mình có tạo ra một abstract class với phương thức rỗng là draw();. Sau đó mình có tạo thêm một lớp con là Rectangle kế thừa lại lớp Shape để sử dụng lại method. Kết quả:

![https://lh5.googleusercontent.com/IWe6OZHJp-INC8am2Fc6-QeKQQt4B81-yQJbv-KZ7ORx0aW7pQeyeG\_ULgIBoRy1x7nUkNu5wlUiRq6r8c8TDLhKOUywjmRRlDR6FojfHawXmD1p6Krn4hl62JetYwg3KtS9LlBO](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.011.jpeg)






Lúc này lớp abstract đóng vai trò như một base class, khai báo tất cả những method cơ bản và cần thiết nhất để các lớp khác có thể tái sử dụng mà không cần viết lại code. Tuy nhiên khi ta extends một class Abstract thì ta phải Override lại toàn bộ methods đã được khai báo.

**3.2. Interface** 

Như ví dụ bên trên mình đã giới thiệu cho các bạn về Interface rồi. Trong Interface thì chỉ có thể khai báo các method rỗng (tức không có body code) để các lớp khác khi implements sẽ khai báo và sử dụng lại methods đó.

Tuy nhiên khi lên Java 8 thì Interface được hỗ trợ defaults methods, lúc này bạn có thể triển khai body code trong một Interface.

Để hiểu rõ hơn về defaults methods bạn có thể đọc bài viết này: 

Vậy sự khác nhau giữa Abstract class và Interface là gì? 



|Abstract Class|Interface|
| :-: | :-: |
|Thể hiện tính trừu tượng <100% |Thể hiện tính trừu tượng 100% (< Java 8)|
|Lớp trừu tượng không hỗ trợ đa kế thừa|Interface có hỗ trợ đa kế thừa|
|Lớp trừu tượng có thể có phương thức static, phương thức main và constructor.|<p>Không có phương thức static, phương thức main và constructor.</p><p></p>|
|Từ khóa abstract để khai báo một lớp abstract|Từ khóa interface để khai báo một lớp Interface.|
|Lớp trừu tượng có thể cung cấp trình triển khai của một Interface|Interface không thể cung cấp trình triển khai cụ thể của lớp abstract.|


`			`Cuối cùng là tính chất thứ 4, **tính đa hình**.

4. **Tâm pháp tầng thứ tư : Polymorphism**

Trong tiếng Anh, “poly” nghĩa là nhiều, “morph” có nghĩa là hình thức. Đa hình có thể là một biến, một chức năng, một đối tượng được đưa vào sử dụng dưới nhiều hình thức khác nhau.









![https://lh4.googleusercontent.com/XVvN6tBx5Wo\_h6YUfjn3b-gIPZxWIlhL-Tcq6AGJBQK8cx7pih\_mA4ppqYNTUl9TrqC4PreJ0bkIn63fTVkagqAumdkzyJdgKD9BTf4VZZ97uIZtiDbcj82AsDhCsouOixwmSf25](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.012.jpeg)






















`	`Để dễ hiểu nhất về tính chất này, bạn có thể liên tưởng đến những diễn viên vậy, ở bộ phim này họ đóng vai ác, đến bộ phim sau họ đóng vai hiền. 



`	`Vậy ta phải sử dụng tính đa hình như thế nào trong lập trình OOP. Trước mắt ta phải hiểu rõ, khi nói đến đa hình là phải đi kèm với kế thừa. Bởi vì để một đối tượng nào đó có thể nhập vai vào một đối tượng khác thù chỉ có thể một đối tượng cha, và ở đây lớp cn sẽ phải ghi đè (Overriding) lại các phương thức của lớp cha.

Ta hãy cùng xem ví dụ dưới đây:![https://lh4.googleusercontent.com/vbM9hjRKzSJ0YBZ\_Jqw4VBroF0JmiX1skijopXlDOZgeQhTMkrfVH0lrzR\_pcT8TXPhvvzIRBKboF\_K\_xbYbb0Q3kYddWveyRsi5EHh0RW84gChpXAZd\_vhTlUAlfV9XEqeLMK3S](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.013.jpeg)![https://lh4.googleusercontent.com/mASCPILzcMD-GJmbm73BiKvsSPBQKIIev\_hX06qBJhjmsTR2jsOp9TjUruIuBEPGDGT-Hu1ZVAcr2kPG011DLuQw3f1wU4liZ98twekCiy1MM7mZCTPBBkmRVP3wmZSEMWKuNdMh](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.014.jpeg)![https://lh5.googleusercontent.com/dp6SrGe9ntJmdMgIX1MMt4nsAYWQWfEk02CQvV15Qdy8mnG8FManTdnCdgasCSNnvT0TfCosz8zNwgAeC-VnZ1yiK5sJy39qsmVE9VEmRHzm286WKXiAr9AEPt2oQvLGWs2Edrww](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.015.jpeg)

Ngoài ra ta còn có Overloading để thể hiện tính đa hình. Vậy sự khác biệt giữa Overriding và Overloading là gì?




- **Overloading** (nạp chồng) Đây là khả năng cho phép một lớp có nhiều thuộc tính, phương thức cùng tên nhưng với các tham số khác nhau về loại cũng như về số lượng. Khi được gọi, dựa vào tham số truyền vào, phương thức tương ứng sẽ được thực hiện. 
- **Overriding** (ghi đè) là hai phương thức cùng tên, cùng tham số, cùng kiểu trả về nhưng thằng con viết lại và dùng theo cách của nó, và xuất hiện ở lớp cha và tiếp tục xuất hiện ở lớp con. Khi dùng override, lúc thực thi, nếu lớp Con không có phương thức riêng, phương thức của lớp Cha sẽ được gọi, ngược lại nếu có, phương thức của lớp Con được gọi.

Để dễ hiểu các bạn có thể hiểu Overloading như sau: Nếu một lớp có nhiều phương thức cùng tên nhưng khác nhau về tham số hay kiểu dữ liệu thì đó chính là nạp chồng phương thức.

![https://lh5.googleusercontent.com/TtMOiwDn0trT4o4Os4Xy-iOXOWwRIGPoeaFEqj7ebtmNdPRqdfGEeuMiHatykWS3BL\_wb8SeO7PUo1vokSsgl9tymzg01ruQnIsSliHwvezuJaNU4Y-NbQWeBKxECvLBKmn12iCU](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.016.jpeg)









![https://lh5.googleusercontent.com/1GyGagFOezpuwYAw5osUxUACNO-7hctAZ2ua18SqAAasrxUQd7N8phnPSOuV7O8LjtK7Hm\_NywSfGEcvWbGCgjJBNSCJNaiQ\_lcI\_0BG2J7vQEAHxe\_8XXYCGO\_zZ3D4QrtyTIKe](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.017.jpeg)







![https://lh5.googleusercontent.com/uUik7GOLUyreZBN1-R2mv1t1S4HDTg6aLoF-1GuN36mkq14ivrUb4EJbrs9dUeUkHDkGeWOYS8xYDMpQl4KdlvKNLEdBHmvhnvMGrdIyaT8qmFs7Mp8SqFFO9MdmG\_56sE1MFFuF](Aspose.Words.89d2e8cc-d0ee-4fae-99b1-6a2bd0854eab.018.jpeg)







Như vậy mình đã giới thiệu cho các bạn về tất cả 4 tính chất trong OOP rồi. Hy vọng bài viết này sẽ giúp các bạn có cái nhìn bao quát hơn về lập trình hướng đối tượng, từ đó sẽ giúp các bạn hiểu rõ hơn về những kiến thức bao la phía sau.

Tài liệu tham khảo:

1. Head First - Java.
1. <https://www.javatpoint.com/abstract-class-in-java>

