# Refactoring
Project: [Jomsaruj's PA4-SecretMEMO](https://github.com/Jomsaruj/PA4-SecretMEMO)
Reference Site: [Refactoring GURU](https://refactoring.guru/refactoring)
## 1. Location: src/encryptdecrypt/WriteFile.java
### Method: writeFile()
```
    if (destFile.exists()) { error("Destination already exists, not overwriting it.");return false; }
    if (!destFile.exists()){
      #codes
    }
    return true;
```
### Issue:
- Hard to read one line statement.
- Unnecessary if() statement.
```
    if (destFile.exists()) {
        error("Destination already exists, not overwriting it.");
        return false;
    }
    #codes
    return true;
```
#### Solve: Separate messy line and DELETE useless block.
#### Benefits:
- Nice clean code and easier to look at.

## 2. Location: src/encryptdecrypt/FileHandler.java
### Method: isValid()
```
    if(strategy.equals("s1") || strategy.equals("s2") ){
        try{ int index = Integer.parseInt(key); }
        catch (NumberFormatException nfe){ error("Invalid key type : key must be a number"); return false; }
    }
    return true;
```
### Issue:
- Hard to read one line statement.
- Multiple strings conditional argument.
```
    List<String> list = Arrays.asList("s1", "s2");  # Note.
    if( list.contains(strategy) ){
        try{ int index = Integer.parseInt(key); }
        catch (NumberFormatException nfe){
            error("Invalid key type : key must be a number");
            return false;
        }
    }
    return true;
```
#### Solve: Adds storage of conditional values and check with contains() method.
#### Benefits:
- Nice clean code and easier to look at.
- Able to adds more conditions and doesn't need extra comparable statements.

