### Buổi 2: Ràng buộc dữ liệu một chiều với Data Binding
Trong Vue.js, ràng buộc dữ liệu một chiều (one-way data binding) là cách thức mà dữ liệu từ mô hình (model) được truyền đến giao diện người dùng (view). Điều này có nghĩa là khi dữ liệu trong mô hình thay đổi, nó sẽ tự động cập nhật trên giao diện, nhưng sự thay đổi trên giao diện sẽ không ảnh hưởng ngược lại đến mô hình.   

 #### HTML
 ```c
<div id="app">
    <p>{{ message }}</p>
    <button @click="updateMessage">Cập nhật Thông điệp</button>
</div>
```
### Javascript
```c
const app = Vue.createApp({
  data() {
    return {
      message: 'Hello, Vue!'
    };
  },
  methods: {
    updateMessage() {
      this.message = 'Thông điệp đã được cập nhật!';
    }
  }
});

app.mount('#app');

```
Giải thích:
```{{ message }}:``` Đây là cú pháp interpolation trong Vue.js, được dùng để hiển thị dữ liệu từ mô hình vào giao diện. Đây là một dạng ràng buộc dữ liệu một chiều. Dữ liệu từ message được hiển thị trong thẻ <p> nhưng thay đổi trực tiếp trên giao diện (view) sẽ không cập nhật ngược lại message.
``` @click="updateMessage":```@ Đây là một event binding, khi người dùng bấm vào nút, phương thức updateMessage sẽ được gọi và cập nhật giá trị của message. Khi giá trị của message thay đổi, giao diện sẽ được tự động cập nhật để phản ánh sự thay đổi này.
Đặc điểm:
•	Dữ liệu được ràng buộc một chiều chỉ có thể di chuyển từ mô hình (model) đến giao diện (view), đảm bảo tính nhất quán của dữ liệu trong ứng dụng.
•	Để cập nhật dữ liệu trong mô hình thông qua giao diện, bạn cần sử dụng ràng buộc hai chiều (two-way binding) với v-model hoặc sử dụng sự kiện để cập nhật dữ liệu trong mô hình như trong ví dụ trên.

