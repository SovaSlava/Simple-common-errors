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
