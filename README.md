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
### Issue:
1. Hard to read one line statement.
2. Unnecessary if() statement.
```
    if (destFile.exists()) {
        error("Destination already exists, not overwriting it.")
        return false;
    }
    #codes
    return true;
```
### Solve: Separate messy line and DELETE useless block.
### Benefits: Nice clean code and easier to look at.
