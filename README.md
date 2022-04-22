# KIẾN THỨC CẦN NẮM CỦA TYPESCRIPT
***
## Định nghĩa
1. Bản chất là được viết trên nền của Js;
2. Cung cấp cho JS thêm chứa năng là khai báo những kiểu dữ liệu;
3. TypeScript chúng ta chỉ dùng khi dev mà thôi, khi dev xong sẽ phải chuyển đổi sang JS thì mới có thể chạy
4. Typescript là mã nguồn mở vì vậy nó miễn phí và có cộng đồng hỗ trợ rất lớn.
5. TypeScript không chỉ hỗ trợ các tính năng mới nhất của JavaScript mà còn bổ sung thêm một vài tính năng như: static typing, OOP,...

***Đọc thêm***: 
- TypeScript cũng đồng thời kế thừa nhiều định nghĩa, khái niệm của đa dạng các ngôn ngữ C#, Java,… nhưng TypeScript lại có yêu cầu cao về trật tự rõ ràng.
- TypeScript được xem là một phiên bản nâng cao hơn của JavaScript vì nó được thiết kế thêm nhiều chức năng tiện lợi hơn, cải tiến hơn từ những điểm yếu của JavaScript như các lớp hướng đối tượng và Static Structural typing, bên cạnh đó TypeScript còn có thể hoạt động rộng rãi cho các ứng dụng của ngôn ngữ Angular2 và Nodejs.
### Tác dụng
1. Phát hiện, bắt lỗi ngay thời điểm đang code
2. Với việc đặt type cho từng biến code của bạn sẽ dễ đoán và debug hơn.
3. Dễ dàng tổ chức code cho các dự án lớn, hỗ trợ OOP mạnh mẽ.
4. TypeScript có một bước biên dịch thành JavaScript, sẽ bắt tất cả các loại lỗi trước khi chúng chạy.
### Ưu điểm so với JavaScript
- Dễ dàng hơn trong phát triển các dự án lớn, được hỗ trợ bởi các Javascript Framwork lớn.
- Hỗ trợ OOP mạnh: Hầu hết các cú pháp hướng đối tượng đều được hỗ trợ bởi Typescript như kế thừa, đóng gói, constructor, abstract, interface, implement, override...v.v
- Cách tổ chức code rõ ràng hơn bởi được hỗ trợ các kỹ thuật mới nhất và hỗ trợ lập trình hướng đối tượng: Hỗ trợ cơ chế giúp kiến trúc hệ thống code hướng module, hỗ trợ namespace, giúp xây dựng các hệ thống lớn nơi mà nhiều dev có thể làm việc cùng nhau một cách dễ dàng hơn.
- Hỗ trợ các tính năng mới nhất của Javascript.
- Một lợi thế của Typescript nữa là mã nguồn mở vì vậy nó miễn phí và có cộng đồng hỗ trợ rất lớn.
Typescript đang được sử dụng ở các Framwork Front-end phổ biến như Angular 2, Ionic,React... cũng như Nền tảng cho back-end như Node-js.

### Nhược điểm so với JavaScript
- Đối với các dự án nhỏ hơn, sử dụng TypeScript có thể làm gia tăng chi phí không cần thiết.
- Ngay như bước biên dịch TypeScript thành JavaScript thôi cũng đã tốn chi phí, tài nguyên rồi.
- Và vì JavaScript được chạy trực tiếp trên trình duyệt, vì vậy đối với các đoạn mã nhỏ, việc làm mới và gỡ lỗi sẽ dễ dàng hơn. Còn đối với TypeScript, chúng ta cần một IDE thích hợp để có thể viết, thử nghiệm và gỡ lỗi nó.
### Vậy khi nào thì nên sử dụng TypeScript, khi nào thì sử dụng Javascript?
1. Typescript nên dùng cho:
    - Dự án lớn.
    - Team size lớn (>5 người)
2. Javascript nên dùng cho:

    - Dự án vừa và nhỏ.
    - Team size nhỏ (1-5 người)

## Create tsconfig.json

1. Sử dụng lệnh: ***tsc --init***;
2. Cấu hình thư mục đầu ra khi compiler: ***"outDir"***
3. Tiến hành compiler: ***tsc --watch***

## Cài đặt môi trường chạy:
1. ***npm i -g typescript***
2. ***npm i -g ts-node***

## Các kiểu dữ liệu trong TypeScript khác Javascript

### Type Annotation

1. Định nghĩa:
    - Có hai dấu chấm ở đằng sau tên biến khởi tạo
    - gắn cho biến đó giá trị một cách chính xác 
    ```ts
        let color: string = 'blue';

    ```
    - Điều này có nghĩa là biến color sẽ nhận kiểu dữ liệu là string và nó chỉ được phép gán 1 chuỗi vào biến đó thôi.
    ***
### Type Inference
1. Định nghĩa:
    - Type inference có nghĩa là typescript sẽ tự động phán đoán kiểu dữ liệu của biến đó là gì thông qua giá trị được gắn ban đầu.
    ```ts
        let color = 'blue';

        console.log(typeof color)// string

    ```
### Union type(Assigning multiple types)
1. Định nghĩa:
    - Khai báo 2 hoặc nhiều kiểu dữ liệu bên trong 1 biến
    
    ```TS
        //Kiểu 1 UNION
        let money:number | string;
        money=10.000;
        money="Mười nghìn đồng";
        // money=true; //ko được nhé
    ```

-----------------------------------

### Array
1. Khai báo: Array có thể được khai báo bằng hai cách sau
    ```ts
        let array1: number[]=[1,2,3]; //cách1
        let array2: Array<number>=[1,2,3]; //cách2

         //mảng với kiểu any
        let list: any[] = [1, true, "free"];

        list[1] = 100;

    ```
### Object
1. Khai báo: Object có thể được khai báo bằng cách sau:
- Cách 1: 
    ```ts
        let employee1: object;

        employee1 = {
            firstName: 'John',
            lastName: 'Doe',
            age: 25,
            jobTitle: 'Web Developer'
        };
        // Hoặc
        let employee2 = {
            firstName: 'John',
            lastName: 'Doe',
            age: 25,
            jobTitle: 'Web Developer'
        };
        console.log(employee1,employee2);
    ```
- Cách 2:  Chỉ định rõ ràng thuộc tính của đối tượng

    ```ts
        let employee: {
            firstName: string;
            lastName: string;
            age: number;
            jobTitle: string;
        };

        //Sau đó gắn đối tượng với các thuộc tính mô tả ở trên
        employee = {
            firstName: 'John',
            lastName: 'Doe',
            age: 25,
            jobTitle: 'Web Developer'
        };

        //Hoặc có thể ghi ngắn gọn hơn

        let employee: {
            firstName: string;
            lastName: string;
            age: number;
            jobTitle: string;
        } = {
            firstName: 'John',
            lastName: 'Doe',
            age: 25,
            jobTitle: 'Web Developer'
        };
    ```

### Tuple
1. Khai báo: Tuple cho phép bạn khai báo mảng với các giá trị có kiểu dữ liệu mà bạn đã biết
    ```ts
        let array1 :[number,string];
          array1=[20,"Manh"];

        // array1=[20,10]; Error
    ```
### Enum
1. Khai báo:
    - là một cách để đặt những cái tên thân thiện hơn với bộ giá trị số.
    - Enum cho phép chúng ta tạo một nhóm, tập hợp các giá trị hằng số trong một nơi chung.
    - Nó sử dụng để khai báo một tập hợp kiểu liệt kê
    ```ts
        enum Phone {
            Iphone,
            Sam=10000,
            Xaomi=20000,
        }
        let phoneName1 = Phone.Iphone;
        let phoneName2 = Phone.Sam;
        console.log(phoneName1);//0
        console.log(phoneName2);//10000

    ```
### Any
1. Khai báo:
    -  Một kiểu dữ liệu mà chúng ta không biết chắc chắn kiểu dữ liệu của nó;
    - Có thể gán bất cứ kiểu dữ liệu nào cho biên any
    ```ts
        let price : any = 100000;
        price="mười nghìn đồng";
        console.log(price); //mười nghìn đồng"
        price=null; 
        console.log(price); //null
    ```
### Unknown
1. Khai báo:
    - Cũng giống như **any**, nhưng có sự khác biệt là không thể thực hiện phép tính nào với biến unknow
    - Nếu muốn thực hiện tính toán thì phải type-cheking

    ```ts
    let count: unknown;

    count=10;

    //  console.log(count+1); //Error
    

    if(typeof count === "number"){// type checking
        count+1;
    }
    ```
#### So sánh Any và Unknown
- unknown được khuyến nghị hơn any vì nó cung cấp khả năng nhập an toàn hơn - bạn phải sử dụng xác nhận kiểu hoặc thu hẹp thành một kiểu cụ thể nếu bạn muốn thực hiện các thao tác trên unknown.

### Void 
1. Khai báo: Được dùng với hàm không trả về giá trị
 ```ts
    function loger(): void {
        console.log("Hello world !!")
    }
 ```

### Never
1. Khai báo: Không thể gán giá trị cho biến never, dùng trong hàm luôn luôn trả về lỗi.
 ```ts
    let v :never;

    // v=undefined //Error
    // v="hello" //Error
 ```

### Type Aliases
1. Khai báo: 
- Tạo một kiểu mới cho kiểu hiện có. Giúp viết code ngắn gọn hơn
- Đặt tên lại cho bất cứ kiểu dữ liệu nào khác
- Có thể export để dùng ở file khác
- có Optional Properties
- có readonly: chỉ đọc chứ ko thể thay đổi giá trị của đối tượng
```ts
//Theo cách cũ->dài dòng
    let person: {name: string, age: number};
 
    let teacher: { name: string; age: number };
    
    let coder: { name: string; age: number };
    
    let blogger: { name: string; age: number };

//Theo cách dùng Alias
   type IPerson = { name: string; age?: number };
 
    let person: IPerson;
    
    let teacher: IPerson;
    
    let coder: IPerson;
    
    let blogger: IPerson;
```
- Cũng có thể đặt tên cho các quy định kiểu dữ liệu:
```ts
    //Cách 1

    type ID = number | string;

    function print1(a:ID){

    }

    print1(10)

    //Cách 2

    type colorDemo= "Green"|"Yellow";

    function print2(a:colorDemo){

    }
        
    print2("Yellow")
```

### Interfaces
1. Khai báo:
- Tạo một khuôn mẫu cho đối tượng tuân theo, nếu đối tượng ko thực thi đúng theo khuôn mẫu interface thì sẽ phát sinh lỗi ngay lập tức
- Chỉ sử dụng được đặt cho object mà thôi
- ***Không thể*** đặt tên cho các quy định kiểu dữ liệu nguyên thủy
- có thể export để dùng ở file khác
- có Optional Properties
- có readonly: chỉ đọc chứ ko thể thay đổi giá trị của đối tượng
```ts
    //Viết code ngắn gọn, đỡ lặp code dễ hiểu hơn
    interface Preson{
        name: string;
        age: number;
        address?: string;
    }

    let teachers: Preson;
    let students: Preson;

    teachers={name:"Dinh",age:30,address:"Đà Nẵng"};
    students={name:"Manh",age:21}
    //Không thể đặt tên cho các quy định kiểu dữ liệu nguyên thủy
    interface tamp = number // Error
```
- Interface cũng có thể khai báo một hàm
```ts
interface SearchFunc {
    (source: string, subString: string): boolean;
}
```
- Indexable Types: ví dụ
```ts
    interface StringArray {
    [index: number]: string;
    }

    let myName: StringArray;
    myName = ["Tôi", "là","Nguyễn","Văn","A",9];// Phần tử của cùng bị lỗi vì không tuân theo khuôn mẫu

    let myStr: string|number = myName[0];
    console.log(myStr);// Tôi
```


#### So sánh giữa interface và Type

1. Kế thừa
<div class="table-responsive">
<table class="table table-bordered table-striped">
  
  <tr>
   <th>Interface</th>
   <th>Type</th>
  </tr>
    
 <tbody>
  <tr>
   <td>
   
```ts
interface Animal {
name: string
}

interface Bear extends Animal {
honey: boolean
}

const bear = getBear() 
bear.name
bear.honey

```
   
   </td>
   <td>

```ts
    type Animal = {
    name: string
    }

    type Bear = Animal & { 
    honey: boolean 
    }

    const bear = getBear();
    bear.name;
    bear.honey; 
```

   </td>
  </tr>
  
 </tbody>
</table>
</div>

2. Type không thể khai báo trùng tên, nhưng interface thì có thể

<div class="table-responsive">
<table class="table table-bordered table-striped">
  
  <tr>
   <th>Interface</th>
   <th>Type</th>
  </tr>
    
 <tbody>
  <tr>
   <td>
   
```ts
interface Window {
  title: string
}

interface Window {
  ts: TypeScriptAPI
}

const src = 'const a = "Hello World"';
window.ts.transpileModule(src, {});

```
   
   </td>
   <td>

```ts
type Window = {
  title: string
}

type Window = {
  ts: TypeScriptAPI
}

 // Error: Duplicate identifier 'Window'.
```

   </td>
  </tr>
  
 </tbody>
</table>
</div>

3. Type có Unions type còn interface thì không:
```ts
type colors = 'blue' | 'green' ;
```
### Null và Undefined( --strictNullCheck trong Typescript 2.0)

***Đọc trước**
 Optional properties là một cách khai báo một biến hoặc một thuộc tính có thể có hoặc không
Tuy nhiên một vấn dề gặp phải khi ta thực hiện những hành động liên quan đến biến hoặc thuộc tính mà không có giá trị sẽ dẫn đến những vấn đề không mong muốn.
Vì vậy ,mà ta cần bật tính năng ***strictNullCheck=true*** trong phần cononfig type;
```ts
    interface Phone{
        name: string,
        price: number,
        quantity?: number
    }

    let Iphone: Phone={
        name: "XSM",
        price:100,
        quantity:1
    }

    const send = (quantity: number) =>{
            console.log(quantity)
    }

    send(Iphone.quantity);//Error
    // Giải quyết lỗi
    if(Iphone.quantity){
    send(Iphone.quantity);
}

```
1. Config trong file ***tsconfig.json***
    ```ts
     "strictNullChecks": true, 
    ```
2. Ví dụ: Giúp cho code của chúng ta chặc chẽ hơn
    ```ts
    // Compiled with --strictNullChecks
        let x: number;
        let y: number | undefined;
        let z: number | null | undefined;
        x = 1;  // Ok
        y = 1;  // Ok
        z = 1;  // Ok
        x = undefined;  // Error
        y = undefined;  // Ok
        z = undefined;  // Ok
        x = null;  // Error
        y = null;  // Error
        z = null;  // Ok
        x = y;  // Error
        x = z;  // Error
        y = x;  // Ok
        y = z;  // Error
        z = x;  // Ok
        z = y;  // Ok
    ```
3. Ví dụ: Kiểm tra việc gán trước khi sử dụng   
```ts
    // Compiled with --strictNullChecks
    let x: number;
    let y: number | null;
    let z: number | undefined;
    x;  // Error, reference not preceded by assignment
    y;  // Error, reference not preceded by assignment
    z;  // Ok
    x = 1;
    y = null;
    x;  // Ok
    y;  // Ok

```
## Class in TypeScript
1. Định nghĩa:
- Là một mô tả trừu tượng (abstract) của nhóm các đối tượng (object) có cùng bản chất.
- Một lớp trong typeScript có thể gồm những thành phần sau:
    + Constructor:  là một dạng đặc biệt của phương thức được sử dụng để khởi tạo các đối tượng. Java Constructor được gọi tại thời điểm tạo đối tượng.
    + Properties: thuộc tính
    + Methods: phương thức
- Demo:
    ```TS
        class Phone {
            name: string
            price: number   
            constructor(name: string, price: number){
                this.name=name;
                this.price=price;
            }

            getName(){
                console.log(this.name);
            }
        }

        let Iphone = new Phone("XSmaxt", 66)

        console.log(Iphone.name);
    ```
2. Access modifiers: Xác định được khả năng hiển thị (truy cập) của các thành phần dữ liệu trong lớp:
    - public:
        + là mặc định, các thành phần được đánh dấu có khả năng truy cập tấp cả;
        + Demo:
            ```TS
                class User{
                    public name: string;
                    age: number;
                    getName(){
                        console.log(this.name)
                    }
                }
            ```
    - private:
        + Chỉ được truy xuất(truy cập) trong chính class của nó;
        + Demo:
            ```ts
                class User{
                    private name: string;
                    private age: number;
                    getName(){
                        console.log(this.name)
                    }
                }
            ```
    - readonly:
        + Có thể được truy cập ở bên ngoài lớp nhưng không thể thay đổi giá trị ;
        + Demo:
            ```TS
                class User {
                    name: string
                    readonly age: number
                    constructor(name: string, age: number){
                        this.name=name;
                        this.age=age;
                    }
                    getName(){
                        console.log(this.name)
                    }
                }
                let user = new User("Manh",21)

                user.name="Quang"

            ```

3. Tính kế thừa(Inheritance):
- Là một lớp con kết thừa những thuộc tính của lớp cha sử dụng từ khóa ***extends***

- Demo:
    ```TS
        class People{
            name: string="manh"
            age: number =0
            constructor(name: string, age: number){
                this.name = name
                this.age = age
            }
        }

        class Student extends People{
            class: string
            idStudent: string
            constructor(name: string, age: number, classNew: string, idStudent: string){
                super(name,age)
                this.class = classNew
                this.idStudent = idStudent  
            }
        }

    ```
***
## Generic Type trong Typescript

## Type Intersection trong Typescript

## Type Assertion và từ kháo ***as***

## Keyof type and Typeof operator trong Typescript

## Utility types trong Typescript
