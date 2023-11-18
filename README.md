# AnalizerLog


1. ### Variable set to same value
```diff
function addMessage(string text) external {
   require(messAdded != true);
   ...
-     messAdded = false;
+     messAdded = true;
}
   ```
or
```diff
if(a == 5) {
-  a = 5;
{
```

2. ### Wrong order of variables in IF statment
```diff
if(a > b) {
-  c = b - a;
+  c = a - b;
}
else {
-  c = a - b;
+  c = b - a;
```

3. ### Add zero value, if we know it
```diff
if(getNumber() == 0) {
-   a = 5 + getNumber();
+   a = 5;
}
```
or
```diff
require(getNumber() == 0);
-   a = 5 + getNumber();
+   a = 5;
```
