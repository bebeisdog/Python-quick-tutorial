# Python 簡介 (WNC)

[TOC]

---

與編譯語言(例如 C、C++、C# )不同的是，直譯語言利用直譯器 interpretor 將程式碼一行一行解析與執行。

||直譯語言|編譯語言|
|:----:|:----:|:----:|
|內容|利用直譯器 interpretor 將**程式碼一行一行解析與執行**。多為動態語言|編譯器(Compiler)將程式碼轉化為機器碼，編譯過程中編譯器會進行**型別檢查、偵錯、最佳化**等，多為靜態語言。|
|特色|程式碼較靈活、程式彈性高、執行速度相對較慢|高效能|
|常見| JavaScript、Python、Ruby|C、C++|


## Variable 宣告

* 在 Python 中不須特別指名型態，但每個 variable 是有型態的 ( type )
    * EX : C++ 中的 int x = 0 ， 在 python 裡只寫 x = 0 ，系統會自動設成 int 形式的物件
* <font color='red'>`=` 就是宣告</font>，EX: `a = 1`
    1. 把 1 放入 Object container 
    2. 指定 Object 名稱是 a
    3. `print(a)` 為指出 a 的物件內容

### Operators

* 整體跟 C++ 沒有差別太多，除了<font color='red'>邏輯運算子 `Logical Operators`</font>
    * python : `and`、`or`、`not`
    * C++    : `&&` 、 `||`、`!`

### 單雙引號以及註解

* Python 中<font color='red'>單雙引號沒有差異，但不能混用</font>
* 註解有三種形式
    ```python
    """
    註解一 (多行)
    """

    '''
    註解一 (多行)
    '''

    # 註解三 (單行)
    ```

---

## 基本語法差異 (for, while, if)

### 縮排
 * python 中使用 tab 或 space 來表示，一個 tab 的長度大概是四個 space
     * `tab` 和 `space` 在<font color='red'>**同一整份檔案**</font>中只能**擇一使用**!
:::danger
在 C/C++ 中，使用 `{}` 表示區塊 (block) ，而在 python 裡，用**冒號**表示開始一個新的區段。 `if` 、 `else` 、 `for` 、 `while` 等 function 後，都需要加**冒號，切記區段都要內縮!!!**
:::

```python
int g = 50;
if (g >= 60){
    cout << "pass";
}
else if (g >= 50){
    cout << "almost pass";
}
else{
    cout << "fail";
} 
```

### if , else , elif 

* Python 中的 else if 表示為 `elif`

```python
g = 50
if (g >= 60):
    print ("pass")
elif g >=50: # else if
    print ("almost pass")    
else:
    print ("fail")    
```

### while

```
while 條件判斷:
    something code
```

### for ... in ...

```
for i in range(起始=0, 終止, 間隔=1)
>>> python 裡的 range() 裡的數字，是有預設起始值的，但沒有預設最終值。 
```

並且是<font color='red'>包含起始值，但不包含終止值</font>

```python
for x in range(4):
    print(x, end='')
>>> 0123    # 包含起始 0 ，不包含終止值

for i in range(11, 1, -2):  ## 也可以讓 range 數字順序是反的
    print(i, end=',')
>>> 11,9,7,5,3,

name = "BEE"  ## 也可用來訪問字串、List 等
for c in name:
    print(c, end =" ")
>>> B E E
```

### match

* 跟 C++ `switch` 用法一致，只有名字不同

```python=
match num:
    case 1:
        return ...
    case 2:
        return ...
    case 3:
        return ...
    case _:
        return ...
```


### Python 例外處理 (try... except)

當 try 區段內的程式發生錯誤時，就會執行 except 裡的內容，如果 try 的程式沒有錯誤，就不會執行 except 的內容

```python
try:                      # 使用 try，測試內容是否正確
    a = input('輸入數字：')
    print(a + 1)
except:                   # 如果 try 的內容發生錯誤，就執行 except 裡的內容
    print('發生錯誤')
    pass                  # 不想執行任何動作，可使用 pass 語法掠過
```

---

## 集合物件差異 (Container)

* Python 基本內建常見的 Container

### List

類似 C++ 的 vector，其數據具有順序性的、可修改、可查閱、資料也可以重複，並在同一個 List 裡，裡面可以放不同型態的資料。以**中括號**框起來為主

> Python 沒有內建如 C/C++ 固定大小的 array，取而代之的是稱為 list ，類似 Linked List 可以自由增減長度

* 新增 :o: 
* 刪除 :o:
* 修改 :o:
* 查詢 :o:

```python
## 可全部一樣 type
students = ['bee', 'obito']
student[-1] # -1 代表最後一個
>>> obito

## 可混合 type
bee_grade = ['bee', 'M103010023', 95]
bee_grade[1:] ## data slice
>>> ['M103010023', 95]

## 也可以在 list 裡面有 list
all_grade = [students, bee_grade]
>>> [['bee', 'obito'], ['bee', 'M103010023', 95]]

## for 也可直接訪問這些 container
for i in student:
    print(i)
>>> bee
>>> obito
```

* `append`、`extend`、`remove`、`sort`、`sorted` 、`len`、`sum`...
* 也具有二維以上的 List

### Tuple

Tuple 跟 List 很像，但它的==資料是不能修改的==，Tuple比較**省空間、速度也比較快**，以**小括號**框起來為主。

* 新增 :x: 
* 刪除 :x:
* 修改 :x:
* 查詢 :o:

:::success
`Tuple` 被宣告完成以後，它是不能新增、刪除、修改元素的。
:::

```python
list_ex = [11, '阿我就爛阿', 87]     ## list
tuple_ex = (11, '阿我就爛阿', 87)    ## tuple
tuple_ex1 = tuple([123, 456, 789])  ## 可以由 List 中建立

tuple_ex[1] = '你'  ## ERROR !!!
tuple_ex.append(66)      ## ERROR !!!
```

### Set

`Set` 就是數學上的集合，裡面的 elemant <font color='red'>**不能重複，也沒有順序性**</font>，也因為他沒有順序性，所以我們沒有辦法取得它的 index 值，它的優點就是能讓我們做集合的運算 (&、|)。

* 新增 :o: 
* 刪除 :o:
* 修改 :x:
* 查詢 :o:

```python
# create a set
temp = set()    ## a empty set
temp = {"BEE", "Alan", "Buck"}
temp = set(["BEE", "Alan", "Buck"])
>>> {'BEE', 'Buck', 'Alan'}
temp_2 = {}    ## this is dict, Not set

# 不會有重複
test = {"Faker", "Faker", "BEE"}
>>> {'Faker', 'BEE'}

print(test[0])   ## ERROR !!!
```

* `add`、`remove`、`clear`...

### Dictionary

Dictionary 表達方式跟 set 一樣，都是由大括號所構成，實際上 Dictionary 是一種比較特別的 set ，因此**裡面的元素是不可以重複的，且也沒有順序性**，但是又具備了一些 list 的特性，像是**可以從索引值來取得它的值**，且==它的索引值是可以自己去定義的!!!== 稱之為 Key。 

* 新增 :o: 
* 刪除 :o:
* 修改 :o:
* 查詢 :o:

1. 由 key，value 所形成的集合
2. Key 的值必須是唯一；可以透過 Key 來檢索取得 Value
3. 形式 { Key:Value }

```python
# create an empty dictionart
empty_dict = {}
empty_dict = dict()

# create a dictionary
## {key:value, key2:value2, .....}，下述這兩個創建方式(7、8行)是一樣的
oil = {'B':'BEE', 'C':'Cat', 66:'live'}   
oil = dict(B = 'BEE', C = 'Cat', 66 = 'live')
>>> {'B': 'BEE', 'C': 'Cat', 66: 'live'}

#  key 可以是 int, string, tuple 等 Immutable Object
std_grade = {1:12, 2:100, 3:98}       ## 學號, 成績
name_grade = {'nick':90, 'jack':50}   ## 姓名, 成績
class_avg = {('A', 'math'):23, ('B', 'eng'):55 }

# 如果 Key 是 List 這種 Mutable Object，是不行的
grade = {['history']:0, 'math':100}   ## ERROR
```

* 何謂 Immutable (不可變) 和 Mutable (可變) 物件? -> [REF Link](https://medium.com/@meghamohan/mutable-and-immutable-side-of-python-c2145cf72747)

---

## Function

def 後方通常會放上函式名稱、輸入參數的小括號，且一樣要縮排

* 需注意名稱不能和變數名稱**重複**

```python
def calaulate(x=3): # can give default value
    result = 0
    while result < 10:
        result = result + x
        if result==5:
            return result, 2
    return result, 2

ans1, x = calaulate(1)
ans2, y = calaulate()
print(ans1)   # 5    # 順序顛倒會出錯
print(ans2)   # 12
```

<font color='red'>由於 python 是直譯程式，必須 「先定義函式，再執行函式」</font>

* 函數可回傳多個結果
* 可設定函式中的函式
    ```python
    def hello(n, msg):
        def h1():       # 內部函式
            return msg
        def h2():       # 內部函式
            return msg*2
        if n == 1:
            print(h1())
        if n == 2:
            print(h2())
    hello(1, 'ok')   # ok
    hello(2, 'ok')   # okok
    print(h2())      # 發生錯誤 name 'h2' is not defined
    ```
* 後續為了嚴謹性，引入類型提示（Type Hints）的概念，可指定函数的參數和返回值指定預期類型。
    * 但只是 <font color='red'>**提示**</font>，你沒有照預期輸入輸出也是可以的
    ```python
    def greet(name: str) -> str:  # 預期 name 是 string，此 func 返回 string
        return name
    
    ans = greet(123)   # 輸出 int
    print(ans)         
    print(type(ans))   # 輸出 int
    >>> 123
    >>> <class 'int'>
    ```
---

## Class

* 建立 Class 的方式類似建立一個 function，使用 `class` 開頭。
* 必須帶有 `self` 參數，代表透過 Class 建立的 Object

```python
class human():
    def __init__(self, age, weight):   
        self.eye = 2
        self.ear = 2
        self.nose = 1
        self.mouth = 1
        self.age = age             
        self.weight = weight      
    def say(self, msg):
        print(f'{self.name} say: {msg}')
    def play(self, thing):
        print(thing)

oxxo = human(18, 68)            # 建立物件時，設定參數數值
print(oxxo.age, oxxo.weight)    # 18, 68
oxxo.say('hello')               # oxxo say: hello
```


### 繼承 (inheritance)

* 繼承表示可以用既有的 Class 去建立一個新的 Class，並加入一些新的東西或修改新的 Class
* 直接用 Class 包住預繼承的 Class

```python
class father():         # fatehr Class
    def __init__(self):
        self.eye = 2
        self.ear = 2
        self.nose = 1
        self.mouth = 1

class son(father):          # son Class Inheritance fatehr class 裡所有的方法
    def language(self):     # son Class具有 language 的方法
        print('chinese')    

oxxo = son()                # 設定 oxxo 為 son()
print(oxxo.eye)             # 印出 2
oxxo.language()             # 印出 chinese
```

### public , private 方法 

* private: 不想讓繼承 (Inheritance) 該類別的子類別 (Subclass) 作使用
* private 建立後，只有該 Class 內部可使用，外部讀取或 subclass inheritance 都不行使用
* private 方法建立 : `__` (雙底線)+ 命名名稱
* Python 默認 Class 所有 element 都是 Public，除了加了雙底線的 private 

```python
class grandpa():
    def __init__(self):    # init 不為 private !
        self.mouth = 1
    def __money(self):     # 建立一個 private 方法 __money
        print('$1000')
    def getMoney(self):    # 建立一個 getMoney 的方法，執行 private 方法 __money
        self.__money()

class father(grandpa):
    def skill(self):
        print('painting')


oxxo = father()
oxxo.getMoney()         # $1000
oxxo.__money()          # 發生錯誤  'father' object has no attribute '_money'
```


---

## 引入 Module

* use `import`，可以引用其他 Module 的程式碼，包含自身建立的`.py`檔案內的 Module
* import 模組名稱、import 模組 as 命名
* from 模組名稱 import 方法

```python=
from matplotlib import pyplot as plt
```

---

## Some bouns Question

### Q1. Python is Pass by assignment

* C++ Pass by Value 是傳給 function 時，複製一份引數 (number) 給函式使用，修改也是修改複製的值
```cpp
#include <stdio.h>
int main()
{
    int num1 = 2;
    printf("before setNum(), num1: %d\n", num1);
    setNum(num1);
    printf("after setNum(), num1: %d\n", num1);
}

void setNum(int num2)
{
    printf("before setting, num2: %d\n", num2);
    num2 = 5;
    printf("after sett ing, num2: %d\n", num2);
}
>>> 2 2 5 2
```



* C++ Pass by Reference 傳給 Function 的是 address ，所以裡外等同於是一個 variable。修改會動到原本的值
```Cpp
#include <stdio.h>
int main()
{
    int num1 = 2;
    printf("before setNum(), num1: %d\n", num1);
    setNum(num1);
    printf("after setNum(), num1: %d\n", num1);
}

void setNum(int &num2)
{
    printf("before setting, num2: %d\n", num2);
    num2 = 5;
    printf("after setting, num2: %d\n", num2);
}
>>> 2 2 5 5
```

* 在 Python 中是一種 Pass by Assignment，Python 傳遞給 function 等都是傳 Object Reference，故它 <font color='red'>需要判斷該物件是不是 Mutable 或是 Imutable 的。</font>
* 才會知道是否會修改到 Variable 本身
* ImMutable example :
    ```python
    number = 7
    def function_1(num):
        print("Before function start, num is", num)
        num = 1
        print("After function ends, num is", num)

    print("Before function start, num is", num)
    function_1(number)
    print("After function start, num is", num)

    >>>
    Before function starts, num is 7
    Before function starts, num is 7
    After function ends, num is 1
    After function ends, num is 7
    ```
* Mutable example : 
    ```python
    object ={
        'name': 'Leo',
        'age' : 25
    }
    
    def function_2(obj):
        print("Before function start, obj is", obj)
        obj['name'] = '9m88'
        obj['age']  = 20
        print("After function ends, obj is", obj)

    print("Before function start, object is", object)
    function_2(object)
    print("After function start, object is", object)

    >>>
    Before function starts, object is {'name': 'Leo', 'age': 25}
    Before function starts, obj is {'name': 'Leo', 'age': 25}
    After function ends, obj is {'name': '9m88', 'age': 20}
    After function ends, object is {'name': '9m88', 'age': 20}
    ```

* ImMutable v.s. Mutable
    ![image](https://hackmd.io/_uploads/rygKgX_Ta.png)



### Q2. Python 沒有 Pointer

* 但 Python 的 Variable 更像是 ，指向 Object 的 Address
* 某種程度上很像 pointer，<font color='red'>尤其對於 Mutable 的 variable</font>

```python
a = [1, 2, 3]
b = a
b.append(4) 
print(a)  # 對於 b 的修改，會反映在 a 上
print(id(a))
print(id(b))
>>> [1, 2, 3, 4]
>>> 137911959091520
>>> 137911959091520
```
* ImMutable 的 variable 則不會，因為在執行 `b=b-1` 時，發現是 ImMutable variable，則會在記憶體創建新的位置給 `b`
```python
a = 3
b = a
b = b - 1 
print(a)  
print(b)
print(id(a))
print(id(b))
>>> 3
>>> 2
>>> 137913240305968
>>> 137913240305936
```

* 思考範例，`=` 是宣告
```python
a = []
b = a
b.append(2)
print(a)
a = [1]
print(a)
print(b)
```


### Q3. Linked-List 差異

* C++ 允許直接訪問 Address 的靜態類型語言，可以直接操作節點的内存地址，使用指针来連接各個節點
* Python 是動態類型的語言，沒有直接操控 Pointer 的能力，但可透過宣告來連結對象

1. Node 建立
    * C++
        ```c++
        struct Node {
            int data;
            Node* next;
            Node(int data) : data(data), next(nullptr) {}
        };
        ```
    * Python
        ```python
        class Node:
            def __init__(self, data):
                self.data = data
                self.next = None
        ```
2. 訪問下一個 Node
    * C++  ```head->next```
    * Python ```head.next```

---

## After Class questions

* 在 Python 的檔案中，我們需要透過縮排來區分 code block，可以透過 tab 或是 space 來達成目的，但是在同一個檔案，他們不能混用嗎?
A: <font color='red'>在同一份檔案中</font>，`tab`、`space`不能混著用，但如果 `import` 的檔案都是用 space，你自己撰寫的檔案可以都用 tab，這樣是可以的
---
* Class 內部可以再包含 Class 嗎?
A: 可以，[Ref](https://www.geeksforgeeks.org/inner-class-in-python/)
---
* import 模組，是指引入一個檔案，還是特定的 function，還是多個檔案
A: 使用 import 關鍵字時，你可以導入一個檔案（模塊）、檔案中的特定函數或類，或者檔案中定義的所有內容。
Bouns: Python會編譯該模組的整個代碼（轉換為字節碼），而不是只編譯用到的部分。不過，這個編譯過程只在模組第一次導入時發生，之後如果再次導入相同的模組，Python會使用已經編譯好的字節碼，除非模組的源代碼被修改過。<font color='red'>這也是`Python`使用`.pyc`文件來存儲編譯後的字節碼，以提高未來加載速度的原因。</font>

---
* 0、NULL、Undefined
![image](https://hackmd.io/_uploads/HkLuoQ6T6.png =400x300)

---
* None 值的 Type
A: NoneType，只有 None 會是這個 Type

---

## REF
1. [Python 是 Pass By Value, Pass by Reference, 還是 Pass by Sharing？](https://medium.com/starbugs/python-%E4%B8%80%E6%AC%A1%E6%90%9E%E6%87%82-pass-by-value-pass-by-reference-%E8%88%87-pass-by-sharing-1873a2c6ac46)
2. [Python Logical](https://www.w3schools.com/python/python_operators.asp)
3. [Mutable vs Immutable Objects in Python](https://medium.com/@meghamohan/mutable-and-immutable-side-of-python-c2145cf72747)
4. [Python 教學](https://steam.oxxostudio.tw/category/python/index.html)