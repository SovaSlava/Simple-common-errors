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
