Một số hàm build-in 
1. Alert 
2. Console 
3. Confirm 
4. Prompt 
5. Set timeout
6. Set interval 

Các loại toán tử 
1. Toán tử số học 
    / Chia 
    % Chia lấy số dư
    ** Lũy thừa
2. Toán tử gán 
3. Toán tử so sánh
4. Toán tử logic (&& ||)

Truthy và Falsy 
- Có 6 gia strij falsy còn lại đều là Truthy 

Kiểu dữ liệu trong Javascript 
1. Kiểu dữ liệu nguyên thủy 
- Number 
- String 
- Boolean 
- Underfined 
- Null 
- Symbol 
2. Dữ liệu phức tạp 
    - Funtion 
    - Object 

Hàm trong JavaScript 
- Kiểu tham số Agruments : Không cần định nghĩa số lượng tham số
- Arguments là một arrays

Function trùng tên : function khai báo sau cùng sẽ ghi đè 

* Các loại hàm 
1. Declaration function 
    <!-- function showMessage(){

    } -->
    - Có thể gọi trước khi định nghĩa
2. Expression function 
    - Không thể gọi trước khi định nghĩa
    <!-- var showMessage = function(){

    } -->
    - Có thế đặt tên hoặc không 
    <!-- var showMessage = function hehe(){

    } -->
    - Các dạng :
    1. call back 
    <!-- setTimeout(function(){

    }) -->
    2.object 
    <!-- var myObject ={
        myFunction: = function(){

        }
    } -->
3. Arrow function

* Làm việc với chuỗi 
1. length 
2. Find Index 
    str.indexOf('Ky tu muon tim kiem', vi tri bat dau tim kiem);
    str.lastIndexOf('Ky tu muon tim kiem');
    Trả về -1 nếu không tìm thấy 
3. Cut string
    str.slice(Vi tri bat dau,vi tri ket thuc);
4. Replace
    str.replace('tu can thay the','Tu thay the')
    str.replace(/tu can thay the/g,'Tu thay the') -> biểu thức chính quy để thay thế tất cả các từ phù hợp
5. Upper case 
6. Lower case 
7. Trim 
8. Split 
    Cắt các phần tử của một chuỗi thành một array
9. Get character by index 
    str.charAt(Vi tri);
    str[0]

* Làm việc với kiểu số 
 -  Phương thức 
 + Number.isFinite() : Xác định xem giá trị đã cho có phải là số hữu hạn hay không. Trả về boolean
 + Number.isInteger() : Xác định xem giá trị đã cho có phải là số nguyên hay không. Trả về boolean 
 + Number.parseFloat(): Chuyển đổi chuỗi đã cho  thành một số dấu phẩy động 
 + Nummber.parseInt(): Chuyển đổi chuỗi đã cho thành một số nguyên 
 + Number.prototype.toFixed(): Chuyển đổi và trả về chuỗi đại diện cho số đã cho, số có chữ số chính xác sau dấu thập phân 
 + Number.prototype.toString(): Chuyển đổi và trả về số đã cho dưới dạng chuỗi 


 * Mảng trong Javascript - Array 
1. Tạo mảng
     var array = [];
2. Làm việc với array 
    1. To String 
    2. Join : Chuyển mảng thành chuỗi với kiểu ngăn cách tùy chỉnh join(' - ')
    3. Pop : Xóa đi phần tử ở cuối mảng và trả về đúng phần tử đó
    4. Push : Thêm 1 hoặc nhiều phần tử vào cuối mảng ( array.push('value','value2'))
    5. Shift : Xóa đi phần tử ở đầu mảng và trả về phần tử đã xóa 
    6. UnShift : Thêm một hoặc nhiều phần tử vào đầu mảng 
    7. Splicing : Xóa một phân tử ở vị trí bất kỳ 
    array.splice(1,1)
    Chèn một phần tử ở một ví trị bất kỳ 
    array.splice(1,0,'DART');
    8. Concat
    9. Slicing (slice(1,2))
    10. forEach() 
        array.forEach(funtion(array,index)){
            //code
        }
    11. Every() 
          array.every(funtion(array,index)){
            //code
        }
    -> Kiểm tra đúng hay sai, các phần tử trong mảng 
    12. Some(): Trẻ về đúng nếu có một phần tử trong mảng thỏa mãn điều kiện
    13. Find() : Dùng để tìm kiếm
        var name = array.find(funtion(array,index)){
            return array.name ='RUBY'
        }
    14. Filter() : Giống find() trả về tất cả phần tử thỏa mãn 
    15. Map() : Cung cấp các thao tác với array  
    16. Reduce()

* Object 
    1. Object Contructor 
    funtion User(name,age ){
        this.name = name ;
        this.age = age ;
    }
    2. Object prototype 
    - Prototype : User.prototype.className = 'F8'

* Math Object 
    1. math.PI 
    2. math.round() : Làm tròn số 
    3. math.abs() : giá trị tuyệt đối 
    4. math.ceil() : Làm tròn trên 
    5. math.floor() : Làm tròn dưới 
    6. math.random() : Số thập phân ngẫu nhiên 
    7. math.min() :  Tìm min trong 1 dãy số
    8. math.max() :  Tìm max trong 1 dãy số

* Lệnh rẽ nhánh if else
* Vòng lặp 
    1. for - vòng lặp với điều kiện đúng 
    2. for/in Lặp qua key của đối tượng 
    3. for/of - Lặp qua value của đối tượng
    4. while - Lặp khi điều kiện đúng 
    5. do/while - Lặp ít nhất một lần , sau đó lặp khi điều kiện đúng