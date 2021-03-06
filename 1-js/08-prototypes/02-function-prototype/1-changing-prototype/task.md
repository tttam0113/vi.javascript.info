importance: 5

---

# Thay đổi "prototype"

Trong mã dưới đây chúng ta định nghĩa một hàm tạo, tạo ra đối tượng và thay đổi prototype mặc định của hàm tạo.

Ban đầu, chúng ta có mã:

```js run
function Rabbit() {}
Rabbit.prototype = {
  eats: true
};

let rabbit = new Rabbit();

alert( rabbit.eats ); // true
```


1. Nếu thêm một lệnh nữa (được tô sáng), thì `alert` sẽ hiển thị gì?

    ```js
    function Rabbit() {}
    Rabbit.prototype = {
      eats: true
    };

    let rabbit = new Rabbit();

    *!*
    Rabbit.prototype = {};
    */!*

    alert( rabbit.eats ); // ?
    ```

2. ...Và nếu mã trở thành như sau(thay đổi một dòng) thì `alert` sẽ hiển thị gì?

    ```js
    function Rabbit() {}
    Rabbit.prototype = {
      eats: true
    };

    let rabbit = new Rabbit();

    *!*
    Rabbit.prototype.eats = false;
    */!*

    alert( rabbit.eats ); // ?
    ```

3. Câu hỏi tương tự nếu mã như sau(thay đổi một dòng)?

    ```js
    function Rabbit() {}
    Rabbit.prototype = {
      eats: true
    };

    let rabbit = new Rabbit();

    *!*
    delete rabbit.eats;
    */!*

    alert( rabbit.eats ); // ?
    ```

4. Và phiên bản cuối cùng:

    ```js
    function Rabbit() {}
    Rabbit.prototype = {
      eats: true
    };

    let rabbit = new Rabbit();

    *!*
    delete Rabbit.prototype.eats;
    */!*

    alert( rabbit.eats ); // ?
    ```
