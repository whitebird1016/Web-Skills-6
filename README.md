# Web-Skills-with-Shikmamaru(6)
![Shikamaru](https://github.com/whitebird1016/Web-Skills-with-Shikmamaru/blob/main/1_HTGSqvOc52yfMwyLhCMjVA.jpeg)
<h2>Function Skills</h2>
<h3>1: Function self-execution</h3>

```
const Func = function() {}(); // Commonly used
(function() {})(); // Commonly used
(function() {}()); // Commonly used
[function() {}()];
+ function() {}();
- function() {}();
~ function() {}();
! function() {}();
new function() {};
new function() {}();
void function() {}();
typeof function() {}();
delete function() {}();
1, function() {}();
1 ^ function() {}();
1 > function() {}();
```
<h3>2: One-time function</h3>

```
function Func() {
    console.log("x");
    Func = function() {
        console.log("y");
    }
}
```
<h3>3: Lazy loading functions</h3>

```
function Func() {
    if (a === b) {
        console.log("x");
    } else {
        console.log("y");
    }
}
// replace with
function Func() {
    if (a === b) {
        Func = function() {
            console.log("x");
        }
    } else {
        Func = function() {
            console.log("y");
        }
    }
    return Func();
}
```
<h3>4: Detect non-null parameters</h3>

```
function IsRequired() {
    throw new Error("param is required");
}
function Func(name = IsRequired()) {
    console.log("I Love " + name);
}
Func(); // "param is required"
Func("You"); // "I Love You"
```
<h3>5: String creation function</h3>

```
const Func = new Function("name", "console.log(\"I Love \" + name)");

```
<h3>6: Handle error messages gracefully</h3>

```
try {
    Func();
} catch (e) {
    location.href = "https://stackoverflow.com/search?q=[js]+" + e.message;
}
```

<h3>7: Handle Async/Await parameters gracefully</h3>

```
function AsyncTo(promise) {
    return promise.then(data => [null, data]).catch(err => [err]);
}
const [err, res] = await AsyncTo(Func());
```

<h3>8:  Handle multiple function return values gracefully</h3>

```
function Func() {
    return Promise.all([
        fetch("/user"),
        fetch("/comment")
    ]);
}
const [user, comment] = await Func();
```
