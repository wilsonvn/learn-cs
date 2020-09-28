# Mastering HTML

## Mục đích

HTML được phát triển ban đầu với mục đích nhằm xác định cấu trúc của các tài liệu được hiển thị trên World Wide Web và tạo sự thuận lợi, đơn giản hơn cho việc chia sẻ thông tin khoa học giữa các nhà nghiên cứu.

Bây giờ, HTML được sử dụng rộng rãi như một ngôn ngữ nền để định dạng trang web như một thông tin cố định.

* HTML là viết tắt của Hyper Text Markup Language (ngôn ngữ đánh dấu siêu văn bản)
* HTML mô tả cấu trúc của một trang web
* HTML bao gồm các phần tử.
* Phần tử HTML giúp trình duyệt xác định cách hiển thị nội dung web.
* Các phần tử HTML được biểu diễn thông qua các tag (thẻ)
* Các tag HTML dán nhãn các mảnh nội dung như "heading" (tiêu đề), "paragraph" (đoạn), "table" (bảng), v.v...
* Các trình duyệt không hiển thị các tag HTML, mà sử dụng chúng để hiển thị nội dung của trang

## Một tài liệu HTML đơn giản

* Thuộc tính <!DOCTYPE html> định nghĩa đây là tài liệu HTML5
* Thuộc tính <html> là phần tử root (gốc) của một trang HTML
* Thuộc tính <head> chứa thông tin meta về tài liệu
* Thuộc tính <title> xác định title (tiêu đề trang) cho tài liệu
* Thuộc tính <body> chứa thông tin meta (thông tin tự mô tả) của tài liệu
* Thuộc tính <h1> định nghĩa một heading (đề mục) lớn
* Thuộc tính <p> định nghĩa một paragraph (đoạn văn)

#### Tại sao cần dùng Thẻ <!DOCTYPE> trong HTML

* [Viblo - Thẻ <!DOCTYPE> trong HTML](https://viblo.asia/p/the-doctype-trong-html-1Je5EmOw5nL)
* [CodeHub - Tại sao lại cần phải dùng thẻ DOCTYPE](https://www.codehub.vn/Tai-sao-lai-can-phai-dung-the-DOCTYPE)

## FORM VALIDATION

Một vài trường dữ liệu khi tạo biểu mẫu nên cần được thu thập dưới góc độ bắt buộc. Vậy nên cần một quy tắc thực thi cho việc đó.

Với các trường thông tin cần thực thi bắt buộc, thêm thuộc tính `required` vào.

```html
<input name="happy" type="text" required>
```

Một vài trường dữ liệu ở dạng giá trị số, chúng ta có thể thiết lập quy tắc xác thực dựa trên việc gán giá trị tối thiểu `min` hoặc tối đa `max` cho nó. 

```html
<input name="happy" type="number" min="1" max="15" required>
```

Với trường dữ liệu văn bản, khi chúng ta muốn giới hạn người dùng nhập vào biểu mẫu một số lượng ký tự nhất định; chúng ta có thể thiết lập thuộc tính `minlength` cho giá trị tối thiểu và `maxlength` cho giá trị tối đa.

```html
<input name="happy" type="text" minlength="5" maxlength="500" required>
```

Với những trường dữ liệu cần độ chính xác thông tin cao, cũng như có một vài nguyên tắc cụ thể để phân loại các dữ liệu để xác thực, lúc đó chúng ta sẽ sử dụng một thuộc tính mẫu `pattern` và gán nó cho một biểu thức chính quy `[regex](Mastering-Regex-d00b9876d7b740ac984da7cdb58e1249)`. Một vài trường hợp sử dụng điển hình như là thanh toán qua thẻ quốc tế.

```html
<input id="payment" name="payment" type="text" required pattern="[0-9]{14,16}">
```

## SEMANTIC HTML

Semantic HTML là cách viết HTML mà sử dụng các thẻ HTML ứng với nội dung được chứa trong nó chứ không phải sử dụng các thẻ theo cách mà chúng ta muốn nội dung trong đó được hiển thị. Nói cách khác, chúng ta bố cục dựa trên các quy tắc hiển thị.

### Thẻ `<nav>`

Thẻ nav khá dễ hiểu, nó dùng để chứa các thẻ `<a>` dẫn đến những nội dung chính của website, nên lưu ý là của website chứ không phải của trang HTML hiện tại, nav thường được bọc trong `<header>` hoặc `<footer>`.

```html
<nav>
  <a href="/html/">HTML</a>
  <a href="/css/">CSS</a>
  <a href="/js/">JavaScript</a>
  <a href="/jquery/">jQuery</a>
</nav>
```

### Thẻ `<main>`

Thẻ `<main>` dùng để chứa nội dung chính của trang, nó sẽ không chứa các thông tin như `<header>`, `<footer>`, `<aside>`,... hoặc những gì thuộc phần intro.

**Trong 1 trang chỉ có 1 thẻ `<main>` duy nhất**

### Thẻ `<article>`

Thẻ article dùng để chứa các nội dung độc lập trong trang. Những nội dung này có thể được cắt ra mang đi nơi khác mà người dùng ở nơi khác đọc vẫn có thể hiểu được, không phụ thuộc vào nội dung chứa trong trang.

Ví dụ như trong trang có chứa phần giới thiệu về 1 quyển sách. Nội dung phần giới thiệu này bao gồm tiêu đề sách, tác giả, tóm tắt, giá,... những nội dung này có thể được trích dẫn ra rồi đem đi trang khác chia sẻ mà người dùng ở trang khác đọc vẫn có thể hiểu được nội dung này là gì. Ở đây, nội dung giới thiệu về trang sách này nên được bọc trong thẻ `<article>`.

### Thẻ `<section>`

Thẻ section dùng để phân chia các phần riêng biệt của trang HTML, ví dụ trong trang có các phần như About, Contact,... thì các phần này sẽ được bọc trong các thẻ `<section>`.

### **Thẻ `<aside>`**

Thẻ aside chứa 1 số thông tin bên lề nội dung chính của trang. Những nội dung chứa trong `<aside>` có thể bị xóa đi mà không làm ảnh hưởng đến nội dung chính của trang. 

Lưu ý, nếu `<aside>` nằm trong thẻ `<article>` thì nội dung nằm trong thẻ `<aside>` đó chỉ chứa thông tin bên lề nội dung chính của `<article>` chứ không phải của toàn trang.

Thẻ này thường được sử dụng cho những thông tin như: chú thích, tài liệu tham khảo, bình luận, thông tin thêm, báo giá,....

Ví dụ ta có 1 trang với nội dung chính là giới thiệu về công nghệ VR, sau đó ta muốn dẫn thêm 1 vài thông tin bên lề về VR cho người xem:

```html
<aside>
  <h3>More Article About VR</h3>
   <ol>
    <li><a href="#">Make a VR Game</a></li>
    <li><a href="#">Learn VR in Unity</a></li>
    <li><a href="#">Build Users Interfaces in VR</a></li>
   </ol>
   <blockquote>
    "Virtual reality was once the dream of science fiction. But the internet was also once a dream, and so were computers and smartphones. The future is coming."  
   <footer>
     - <cite><a href="https://www.facebook.com/zuck/posts/10101319050523971">Mark Zuckerberg</a></cite>
   </footer>
     </blockquote>
 </aside>
```

### **Thẻ `<div>`**

Thẻ `<div>` là thẻ không hề có Semantic meaning. Nó chỉ dùng để bọc những nội dung có liên quan đến nhau lại. Khi không tìm được thẻ thích hợp để bọc phần nội dung đó thì ta sẽ sử dụng thẻ div.

Ví dụ như phần intro của trang web, nó không thể nằm trên header cũng không thể nằm trong main, khi ấy ta sử dụng thẻ div để bọc các thông tin đó lại.

Ngoài ra, người ta còn sử dụng thẻ `<div`> để bọc những nội dung cần format giống nhau bằng CSS, cũng như tách trang thành từng phần nhỏ, để trình duyệt có thể render từng phần 1, tăng tốc độ hiển thị đến người dùng thay vì phải load toàn bộ trang mới render.

### Thẻ `<figure>` và `<figcaption>`

### Thẻ `<header>` và `<footer>`

- Thẻ `<header>` bọc những thông tin giới thiệu về toàn trang web hoặc navigation bar.
- Thẻ `<footer>` bọc những thông tin về trang web, thẻ footer của toàn trang thường chứa contact information, copyright information,...
- **LƯU Ý:** Có thể sử dụng nhiều thẻ `<header>` và `<footer>` trong trang theo nhiều trường hợp.
    - Đối với thẻ `<header>`, nó có thể chứa thông tin giới thiệu về element chứa nó (thường là các section).
    - Đối với thẻ `<footer>`, nó có thể chứa những thông tin mở rộng cũng cho element chứa nó, tùy thuộc element đó là gì.

