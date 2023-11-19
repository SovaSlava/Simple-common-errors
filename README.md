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

4. ### Assign the same value to variable in IF and ELSE blocks
```diff
if(...) {
-  c=5
}
else {
-  c=5
}
```

5. ### Always True If statment
```diff
-  if(a==b || b !=a )
+  if(a==b) {
+    ...
+  }
+  else {
+   ...
+  }
```
or
```diff
-  if(a==b && b==a)
```

6. ### The same result of IF statment
```diff
-  result = a==b ? true, true
+  result = a==b ? true, false
```

7. ### Same error message
```diff
require(a==5, "Wrong number");
require(b==7, "Wrong number");
```
or
```diff
if(a==5) error WrongNumber();
if(b==7) error WrongNumber();
```

8. ### Call public payable function from other nonPayable function
```diff
function a() public  payable {
        ...
}

function b() external {
   a();
}
```

9. ### Different role on second-call function
```solidity

function a() onlyRole("admin") {
   b();
}

function b() onlyRole("owner")

```

10. ### Multiply by 1
```diff
-   uint amount = getBalance() * 1;
+   uint amount = getBalance();
```
