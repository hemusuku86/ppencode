# Can we write python code with only symbols?
JSFuck, JJencode... There are many projects that writes JavaScript with only symbols.<br>
but, **python is not**.
# Why?
It's simple, python's types are stricter than JavaScript's.<br>
For example, in JavaScript, you can do "toString" method with just concatenate Array or String.
```js
1+[] => "1"
""+500 => "500"
```
But, in python...
```py
1+[] => TypeError: unsupported operand type(s) for +: 'int' and 'list'
""+500 => TypeError: can only concatenate str (not "int") to str
```
and there're more reason that makes hard to write python with only symbols.<br>
You can get properties or methods like JSON in JavaScript.
```js
"abc"["length"] => 3
(3)["toString"] => function toString...
```
It doesn't work in python, too.<br>
You can get attributes with str by using getattr function, but you have to get the getattr function with only symbols. (its nearly or literally impossible)
# my idea
Now, i can write any python code with this subset: `exc("+>%)`<br>
First, you can make True/False with: `"+">""`, `"">""`.<br>
In python, **bool is a subclass of int.**
It makes this possible:
```py
+True => 1
+False => 0

+("+">"") => 1
```
Congratulations, **we got ints with only symbols!**<br>
Now, you can get any positive int: `1+1+1+...`<br><br>
Now we are going to get str.<br>
But unfortunately, here's the first wall. (first part to use chars that isn't symbols...)<br>
In python, you can make chars from int with:
```py
"%c" % ascii_charcode
```
So, we can get any str with:
```py
"%c"%(+("+">"")+("+">"")+("+">"")+...)
```
But, it is so difficult, or impossible to find the way to get "c" with only symbols. (that's why i made this repo, i need your help)<br>
```py
# idk are these will be useful, but here's something maybe can make "c":

type("") => str
type("")(type("")) => str(str) => "<class 'str'>"
type("")(type(""))[1] => "c"
# You have to get type function, str function or <class 'str'> with only symbols.

# or, you can use octal escape
"\143" => "c"
# But it's useless because you have to eval this, getting eval function and backslash is way too hard
```
Now, we got strs, so its time to execute them!
```py
exec("%c"%(+("+">"")+("+">"")+("+">"")+...))
```
... Here's the second wall..., **How we can get the exec function?**<br>
... Of course, this is way too harder than getting "c". There's high probability that it's literally impossible.<br><br>
So, Now i have 2 huge walls to write python with only symbols.<br>
If you have a genius idea, please share me!<br>
**You don't have to stick to use subset like `exc("+>%)`, If you can write python with only symbols, Even if your subset is completely different, It's a big step.**
