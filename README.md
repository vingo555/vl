# vl language specification

vl language is a common computer language and it is not realistic so far. 
the following information is just some of thought about ideal computer language.

some of basic rule for the language should be :

* as easy/simple as possible
* as powerful as possible
* easy to learn and easy to use

## keywork for vl
`
  if else  for   
  return 
  id type sizeof
  nil true false string
`

## data type for vl

basic date type 

> int8  int16, int32 int64, int128, int256, int512

> uint8, uint16, uint64, uint128, uint256, uint512

> float double

> char , wchar  nil, 

>string, wstring

> any

> []  {}

## string defintion

    hello = "you are welcome to here"
    hello = "book's name is \"computer and chip desip\", you can borrow it "

    hello = 'you are 
        welcome to here and it\'s mine.'

    hello:string = 'hello world'
    hello:wstring = 'hello,world'
    hello:wstring = '你好'

and it also support the escapes of type which is compatible with c luanguage.

* \n (New line) – We use it to shift the cursor control to the new line
* \t (Horizontal tab) – We use it to shift the cursor to a couple of spaces to the right in the same line.
* \a (Audible bell) – A beep is generated indicating the execution of the program to alert the user.
* \r (Carriage Return) – We use it to position the cursor to the beginning of the current line.
* \\ (Backslash) – We use it to display the backslash character.
* \’ (Apostrophe or single quotation mark) – We use it to display the single-quotation mark.
* \” (Double quotation mark)- We use it to display the double-quotation mark.
* \0 (Null character) – We use it to represent the termination of the string.
* \? (Question mark) – We use it to display the question mark. (?)
* \nnn (Octal number)- We use it to represent an octal number.
* \xhh (Hexadecimal number) – We use it to represent a hexadecimal number.
* \v (Vertical tab)
* \b (Backspace)
* \e (Escape character)
* \f (Form Feed page break)


### function defition
+ fnName(argument list) return value {}
+ there may many return value
+ if argument no type declaration which mean template which match different type automatically.
+ no keywork for lambda function 

```c
  add(x:int32 , y: int32) int32 {
    return x + y;
  }
```

no template keyword (type declarition)

template function like 
```c
  add( x, y ) type(x) {
    return x + y ;
  }

  //anonymous function
  fn = (x,y) type(x) {
    return x + y ;
  }

```

## struct definiton
```c
  //4 bytes alignment structure

  struct:4 point {
    x : int32  
    y : int32
  }
  //1 byte alignemnt
  struct:1  coordination {
    top: int64
    left : int64
    right :int64
    botton : int64
  }

  fab(x) type (x)  {
    return x * fab(x - 1)
  }

```

```c
main() int {
   a = 5 
   fn = (a , b ) type (a) { return a + b ; }
   a: int8 = 5;
   str = "youare good"
   hello = 'you are back to "you are """'
   record = [10] ; 

  while( a > 0 ) {
       a--
       if(a == 3) break

  }
  return 0
}

```

## comment
 there are two types of comment 
 + one line comment. using '//' like c lanuage for one line comment
 + multiply line comments. using /* */ like c language for multi lines comments

## array 

```c
  //int array,lenth 5
  record:int[5] = [1,3, 5, 7, 9]
  //init 1000 element arary with 0
  //array will use the left value to fill the rest of space.
  value:int[1000] = [0, ...]
  //array : 2, 3, 3, 3, 3
  count:int[5] = [2,3]
  //not initialize int array
  cout: int [5]

  //generical type array, lenth 5
  cout : [5]

  //araray 1,1,1, 2, 2, 2
  count:int[6] = [{1,3}, {2,3}]
  
  //auto type inference, string array, length 10
  temp:[10] = ["you","are","not"]
   
  //int type tuple which refer to array
  right int[] 
  v = temp[0:3]

  //slice copy from reference
  z := temp[0:3]
```

