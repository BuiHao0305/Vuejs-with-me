#### Event Modifiers
Trong __Vue.js__, __Event Modifiers__ là các cú pháp đặc biệt được sử dụng để sửa đổi hành vi của các sự kiện trong các biểu thức xử lý sự kiện. `Event Modifiers` giúp bạn dễ dàng thực hiện các thao tác phổ biến mà không cần phải viết code JavaScript phức tạp trong phần xử lý sự kiện. Các Event Modifiers thường được sử dụng kèm với các sự kiện trong template của Vue.

Dưới đây là một số __Event Modifiers__ phổ biến trong __Vue.js__:

`stop`: Ngăn chặn sự kiện lan truyền lên các thành phần cha `(event.stopPropagation())`.
```
<button @click.stop="doSomething">Click me</button>
```

.`prevent`: Ngăn chặn hành vi mặc định của sự kiện `(event.preventDefault())`.
```
<form @submit.prevent="onSubmit">Submit</form>
```
.`capture`: Đăng ký sự kiện dưới dạng sự kiện bắt đầu từ cha trước khi đến con (event capturing).

```
<div @click.capture="doSomething">Click me</div>
```
.`self`: Chỉ kích hoạt sự kiện nếu sự kiện được phát ra từ chính thành phần đó, không phải từ các thành phần con.

```c
<div @click.self="doSomething">Click me</div>
```
.`once`: Chỉ cho phép sự kiện được kích hoạt một lần.
```c
<button @click.once="doSomething">Click me once</button>
```
.`passive`: Cải thiện hiệu suất bằng cách thông báo cho trình duyệt rằng sự kiện không bao giờ gọi `preventDefault()` (sử dụng cho sự kiện cuộn).
```c
<div @scroll.passive="onScroll">Scroll me</div>
```
Ví dụ cụ thể, bạn có thể thấy rằng việc sử dụng .`prevent` và .`stop` có thể giúp bạn ngăn chặn việc form được gửi đi và ngăn chặn sự kiện click lan truyền lên các thành phần cha:
```c
<form @submit.prevent>
  <button @click.stop="doSomething">Submit</button>
</form>
```
Như vậy,__Event Modifiers__ giúp code __Vue.js__ của bạn trở nên ngắn gọn và dễ hiểu hơn khi xử lý các sự kiện.

