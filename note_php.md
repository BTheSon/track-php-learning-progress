## Note php

### 1. String
- __các hàm liên quan__

    - `strlen($str)` : lấy độ dài chuỗi (tính cả dấu cách và espace)

    - `str_count_word($str)` : đếm số lượng từ

    - `strrev($str)` :đảo ngược chuỗi

    - `strpos($str, $find_str)` :  trả về vị trí của chuỗi `$find_str` trong `$str`

    - `str_replace($find, $replace, $str)`

- __Nối chuỗi__
    - `$c = $a . $b` nối `$b` vào sau `$a` và gán cho `$c`
    - `$a .= $b` ghép `$b` vào sau chuỗi `$a`
    - `$a = "{str}"` : chèn trực tiếp chuỗi `$str` vào vị trí chỉ định
        - vd
        ```
        $s1 = "love";
        $s2 = "i {$s1} u" // tương đương $s2 = "i love u"
        $s2 = "i $s1 u"   // như kết trên nhưng không an toàn dễ lỗi
        ```
        - _Lưu ý_: chỉ hiệu quả với dấu " " (nháy kép) còn dấu ' ' (nháy đơn) thì không được phép


### 2. Kiểu dữ liệu
- Các loại dữ liệu
    - String
    - Interger
    - Float
    - Boolean
    - Array
    - Object
    - NULL
    - Resource

### 3. Các loại toán tử
- Các loại dữ liệu
    - Số học
    - chuyển nhượng
    - So sánh
    - Tăng và giảm
    - Logic
    - Chuỗi
    - Mảng
    - Gán có điều kiện
<details>
    <summary> Chi tiết từng loại <br>
        > <i>lưu ý chỉ nêu những thứ chưa học</i>
    </summary>

- So sánh
    - Không so sánh type
        - `==` 
        - `!=` 
    - So sánh type
        - `===`
        - `!==`
- Logic
    - `or` hoặc 
    - `and` và
    - `xor: (true xor false) = true;  (false xor true) == true`
- Toán tử chuỗi
    - `$c = $a . $b` nối `$b` vào sau `$a` và gán cho `$c`
    - `$a .= $b` ghép `$b` vào sau chuỗi `$a`
    
</details>

### 4. Mảng
1. __Các loại mảng__
    - Mảng chỉ số
         ```
        $arr = array("element0", "element1", "element2");
        $arr[1] // = element1
        ```
    - Mảng dạng json
        ```
        $arr = array("key1" => "value1", "key2" => "value2");
        $arr["key1"];   // "value1"
        ```
        - __Giải thích__: 
            - là mảng lưu dạng key-value
            - key phải là kiểu nguyên thủy(int, string, float, ...) 
            - value có thể là bất kiểu kiểu dữ liệu nào
2. __Duyệt__
    - foreach()
        ```
        foreach($arr as $value) {
            // dosomething with {$value}
        }
        ```
    - for()
        ```
        for ($i = 0; $i < count($arr); ++$i) {
            // do somthing with {$arr[$i]}
        }
        ```
3. __Thêm phần tử__
    - vd 1:
        ```
        $arr  = array("son" , "dung", "meo");
        $arr[] = "dog";
        ```
        kết quả:
        ```
        $arr[0] = "son"
        $arr[1] = "dung"
        $arr[2] = "meo"
        $arr[3] = "dog"
        ```
        - _Giải thích_: khi không truyền index thì "dog" được thêm vào cuối mảng
    - vd 2 
        ```
        $arr  = array(1 => "one", "son" => "meo" , "tuan" => "d co ny");
        $arr[] = "he"
        ```
        kết quả:
        ```
        $arr[1] = "one"
        $arr["son"] = "meo"
        $arr["tuan"] = "d co ny"
        $arr[2] = "he"
        ```
        - _Giải thích_: 
            - khi làm như trên thì `"he"`  sẽ được thêm vào cuối
            - key của ptu mới thêm vào mặc định sẽ là key có kiểu int lớn nhất và cộng thêm một vào(như ví dụ là `1 => "one"`)
            - mấy key khác có kiểu là string hết nên không tính


4. Hàm liên quan
    - `count($arr)` : hiển thị số lượng phần tử trong `$arr`
    - `sort($arr)` : xếp mảng theo thứ tự tăng dần
    - `rorf($arr)` : xếp mảng theo thứ tự giảm dần

### 5. Hàm
1. Khai báo
    ```
    funtion ten_ham () {
        // do something
    }
    ```
2. Tham số
    - Thông thường
        ```
        funtion ten_ham($pranma1, $parama2) {
            // do something
        }
        ```
    - Giá trị mặc định cho tham số
        ```
        funtion ten_ham($pranma1 = "default") {
            // do something
        }
         
        ```
        - __giải thích__ :  nếu không truyền tham số vào hàm thì  mặc định tham só $parama = "default" 
    - Định kiểu cho tham số
        ```
        funtion ten_ham(int $a) {
            // do something with int type
        }
        ```
        - __Giải thích__: thông báo rằng hàm này chỉ nhận tham số kiểu int
3. Giá trị trả về
    ```
    funtion ten_ham() {
        // do something

    }
    ```
4. 
### F. Những hàm thông dụng
- `isset($v)` kiểu tra biến `&a` có tồn tại không
- `var_dump($var)` hiển thị thông tin chi tiết về biến `$var`
- `declare()` : cái gì đó tui chưa tìm hiểu
- `print_r($variable)` : hiển thị raw data của biến `$variable` (có thể dùng hiển thị raw data của một mảng)
- `$arr = explode($delimiter, $string);` : hàm tách chuỗi `$string`  thành mảng `arr` cách nhau bằng `$delimiter`
- `$s = implode($delimiter, $arr);` : ngược lại với hàm `explode()`
- `header("Location = {$file_name}")` : khi gọi hàm này thì trang php hiện tại sẽ chuyển sao tran php có tên `$file_name`