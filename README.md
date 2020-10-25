# Refactoring
## Location: src/encryptdecrypt/WriteFile.java
### Method: writeFile()
```
    if (destFile.exists()) { error("Destination already exists, not overwriting it.");return false; }
    if (!destFile.exists()){
      #codes
    }
    return true;
```
### Issue: ...
```
    if (destFile.exists()) { error("Destination already exists, not overwriting it.");return false; }
    #codes
    return true;
```
### Solve: ...
### Benefits: ...
