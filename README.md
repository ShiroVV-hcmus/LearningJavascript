#Variables, Operators and Esxpressions in JS
1. Variables:
- Ex: **var num = 2;**
- Đặt tên:
    + `Có kí tự, số, _ và $`
    + `Không thể bắt đầu là số`
    + `Có phân biệt chữ hoa-thường`
    + `Tên không được là những từ đặc biệt: ` **var**, **if**, **do**, **while**, ...
    ___ 
2. Data types in JS:
- Number: **number**: 0, 1.5, ..., **Infinity**, **NaN**, ...
    > Nghĩa là cho dù là số, số vô cực hay không phải số thì nó vẫn là "number"

    + In-Built Number Function:
        Function: 
        <br>
        - **toString()** <> **parseInt()**
        <br>
        - **toString()** <> **parseFloat()**
        <br>
        - **parseInt()** thì làm tròn:
            > "11.5" --> 11
        - **toFixed(x)** làm tròn đến x chữ số sau dấu phẩy.
- String: `"something"` <br>
    > Muốn viết dấu " thì viết \", ' thì \'
    <br>
    
    >   \0	the NULL character <br>
            \'	single quote <br>
            \"	double quote <br>
            \\	backslash <br>
            \n	new line <br>
            \r	carriage return <br>
            \v	vertical tab <br>
            \t	tab <br>
            \b	backspace <br>
            \f	form feed <br>
            \uXXXX	unicode codepoint <br>
            \u{X} ... \u{XXXXXX}	unicode codepoint {{experimental_inline}} <br>
            \xXX	the Latin-1 character <br>
            

    + In-Built String Function:
        - **length()**: Return length of string.
        - **indexOf(string)**: Return index of a string inside another string.
        - **lastIndexOf(string, int)**:
        Return last index of a string inside another string, from position int. (`indexOf(), and lastIndexOf() return -1 if the text is not found`)
        - **search()**: searches a string for a specified value and returns the position of the match.
        <br>
        > **Extracting String Parts**: <br>
            There are 3 methods for extracting a part of a string: <br>
            `slice(start, end)` slice out a portion of a string from position start to position  end.<br>
            `substring(start, end)` <br>
            `substr(start, length)` <br>

        > **Replacing String Content**: <br>
            `replace()`: replaces a specified value with another value in a string. Replaces only the first match. Return a new string. <br>
            Ex: `str = "Please visit Microsoft!"; <br>
                var n = str.replace(/MICROSOFT/i, "W3Schools");` <br>
                =>  Replace 1 lần <br>
            Ex: `str = "Please visit Microsoft and Microsoft!";<br>
                var n = str.replace(/Microsoft/g, "W3Schools");` <br>
                => Replace all.
        
        >**Converting to Upper and Lower Case**: <br>
        `toUpperCase()`:

        - **concat()**: Nối 2 hoặc nhiều chuỗi.
        <br> Ex: `"Hello" + " " + "World!"` = `"Hello".concat(" ", "World!");`
        - **trim()**: Xoá khoảng trắng dư thừa ở đầu và cuối chuỗi.
            >**Define a trim function**: <br>
            if (!String.prototype.trim) { <br>
                String.prototype.trim = function () { <br>
                return this.replace(/^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g, '');<br>
                };<br>
            }<br>
            var str = "       Hello World!        "; <br>
            alert(str.trim());

        - **split(arg)**: Convert string to array. <br>
            Nếu arg == "" thì trả về mảng các kí tự <br>
            Nếu arg == null thì trả về string <br>
            Nếu arg là kí tự gì đó thì trả về index[0] của mảng được tạo ra

- Null: `biến có giá trị là null (value null)`.
- Undefined: `biến không có giá trị (no value)`, `biến chưa được định nghĩa`.
3. Conditional Statement: `like C++ :))`
4. Operators:
- Arithmetic Operators: `+ - * / % ++ --`
- Assignment Operators: `= += -= *= /= %=`
- Comparison and Logical Operators:
    <br> 
    > `==` chỉ so sánh giá trị: 5=='5' -> `true`
    <br>

    >`===` thì so sánh cả giá trị và `kiểu dữ liệu`: 5==='5' -> `false` 
5. Coercion: `Change data type`
    > `"ahihi"` + `123` = `"ahihi123"` <br>
    **string** + **number** = **string**

    > `"ahihi"` + `true` = `"ahihitrue"` <br>
    **string** +/- **boolean** = **string**

    > +`"2"` = `2` <br> 
    **nothing** + **string** = **number**, chỉ khi string có thể là số

    > +`'apple'` = `NaN`

    > `2` >= `'2'` --> `true` <br>
    --> JS convert '2' to number then compare with 2.

    > Số `0`, `''` (string rỗng) và `undefined` == `false`

    ___
    
    > Chuyển từ số sang chuỗi: `String(num)` <br>
    Chuyển từ chuỗi sang số: `Number(string)`


6. Object and Array: <br>
- Object:  <br>
    Ex: 
    > var: car = { <br>
        name: "Vinfast", <br>
        MFG: 2020 <br>
        speed: function(){ <br>
            return 1;<br>
            }<br>
    } <br>

    => `name` or `MFG` or `speed` is called `properties` <br>
    Objects can also have `methods`.
    Methods are actions that can be performed on objects.
    Methods are stored in `properties` as `function definitions`. <br>
    A method is `a function` stored as `a property`.<br>

    **Notes**: Avoid String, Number, and Boolean objects. <br>
    Ex: `var x = new String();        
        var y = new Number();        
        var z = new Boolean(); `<br>

- Array: Mảng có thể có phần tử ở các kiểu dữ liệu khác nhau<br>
    JavaScript does not support arrays with named indexes.<br>
    > Creating an Array: `var array_name = [item1, item2, ...];` <br>
    or `var cars = new Array("Saab", "Volvo", "BMW");` <br>
    => The two examples above do exactly the same. For simplicity, readability and execution speed, use the first one.<br>
    `var cars = [
    {type:"Volvo", year:2016},
    {type:"Saab", year:2001},
    {type:"BMW", year:2010}
    ];`

    >**Properties**:<br>
    - length

    >**Methods**<br>
    - **push()**: Adding new Array Elements (to the last) and returns the new array length. <br>
    - **pop**: remove the last item of array. <br>
    ___
    - **isArray()**: Return true if it is an array, else return false.<br>
    `function isArray(x) {
        return x.constructor.toString().indexOf("Array") > -1;
    }`
    ___
    - **toString()**: Convert Arrays to Strings
    - **join()**: Convert Arrays to Strings <br> 
    It behaves just like `toString()`, but in addition you can `specify the separator`: <br>
    `var fruits = ["Banana", "Orange", "Apple", "Mango"];
    document.getElementById("demo").innerHTML = fruits.join(" * "); ....       
    Result:    Banana * Orange * Apple * Mango`<br>
    ___
    - **shift()**: remove the first array element and "shifts" all other elements to a lower index.
    - **unshift()**: adds a new element to an array (at the beginning), and "unshifts" older elements.
    ___
    - **splice()**: add new items to an array and return a new array is cut<br>
    Ex: `var fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.splice(2, 0, "Lemon", "Kiwi");` <br>
    -> The first parameter (2) defines `the position` where new elements should be added (spliced in). <br>
    The second parameter (0) defines `how many elements should be removed`. <br>
    The rest of the parameters ("Lemon" , "Kiwi") define the `new elements` to be added. <br>
    ___
    - **concat()**: create a new array by merging (concatenating) existing arrays.<br>
    Ex: `var myChildren = myGirls.concat(myBoys);`<br>
    ___
    - **sort()**: sort an array.
        - Sorting ascending:<br>
        `   var points = [40, 100, 1, 5, 25, 10];
            points.sort(function(a, b){return a - b});`<br>
        - Sorting descending:
        `   var points = [40, 100, 1, 5, 25, 10];
            points.sort(function(a, b){return b - a});`
    - **reverse()**: reverse (đảo ngược) the elements in an array.
    ___
    - **max**: `Math.max.apply(null, [1, 2, 3])` is equivalent to `Math.max(1, 2, 3).`
    - **min**: `Math.min.apply(null, [1, 2, 3])` is equivalent to `Math.min(1, 2, 3).`
    
    => For number :))
    
    >**Array Iteration Methods**:<br>
    - **forEach()** method calls a function (a callback function) once for each array element
        >var txt = "";<br>
        var numbers = [45, 4, 9, 16, 25];<br>
        numbers.forEach(myFunction);<br>
        function myFunction(value, index, array) {<br>
        txt = txt + value + "<br>";<br>
        }<br>
    - **map()**: creates a new array by performing a function on each array element, does not execute the function for array elements without values and does not change the original array.<br>
    - **filter()**: creates a new array with array elements that passes a test. <br>
        > var numbers = [45, 4, 9, 16, 25];<br>
        var over18 = numbers.filter(myFunction);<br>
        function myFunction(value, index, array) {<br>
            return value > 18;<br>
        }<br>

    - **reduce()**: runs a function on each array element to produce (reduce it to) a single value.
    - **every()**: check if `all` array values pass a test.
    - **some()**: check if `some` array values pass a test.
    ___
    - **lastIndexOf()**: is the same as `Array.indexOf()`, but returns the position of the last occurrence of the specified element.
    - **find()**: returns the value of the first array element that passes a test function.
    - **findIndex()**: returns the index of the first array element that passes a test function.
    ___
    >**The Difference Between Arrays and Objects**:<br>
    In JavaScript, arrays use `numbered indexes`.<br>
    In JavaScript, objects use `named indexes`. <br>

    >**When to Use Arrays. When to use Objects**:<br>
    You should use objects when you want the element names to be strings (text). <br>
    You should use arrays when you want the element names to be numbers.

    >**[ ]** and **new Array()**: <br>
    var points = new Array();     // Bad <br>
    var points = [ ];              // Good<br>
    Because, when you use `var points = new Array(40);`, you create an array with `40 undefined elements`.

7. Loops:
- **for** - loops through a block of code a number of times
- **for/in** - loops through the properties of an object
- **for/of** - loops through the values of an iterable object
- **while** - loops through a block of code while a specified condition is true
- **do/while** - also loops through a block of code while a specified condition is true
8. Function: 
    >function myFunction(p1, p2) { <br>
    return p1 * p2;   // The function returns the product of p1 and p2 <br>
    } <br>

    Almost like C++ :))
    - **call()**: takes arguments separately. 
    - **apply()**: takes arguments as an array.
    > Hai hàm này đều dùng để gọi thuộc tính từ 1 Function nào đó, yeah, Funciotn in JS like Class in C++
9. Document Object Model (DOM):<br>
    > Document Object Model (DOM) is a platform and language-neutral interface that allows programs and scripts to dynamically access and update the content, structure, and style of a document. <br>
    ___
    Finding HTML Elements: 
    > Methods:
    - **getElementByID("`id`")**:
    - **getElementByClassName("`class`")**:
    - **getElementByTagName("`tag-name`")**:
    >Query Slector: use CSS selector to select HTML elements
    - **querySelector()**:
    - **querySelectorAll()**:


    > Properties:
    - **innerHTML**


    



    



    



