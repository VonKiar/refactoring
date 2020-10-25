# Refactoring
## League’s Insights

<details>
  <summary> ITERATION 1 </summary>
  <p> 
    '''
    if (destFile.exists()) { error("Destination already exists, not overwriting it.");return false; }
    if (!destFile.exists()){
      if(isValid(key,strategy)) {
        try (FileWriter out = new FileWriter(destFile);) {
          Cipher enc = new AlphabetShiftCipher();
          if (strategy.equals("s2"))  enc = new UnicodeCipher();
          if (strategy.equals("s3")) enc = new KeyWordCipher();
          if(strategy.equals("s4")) enc = new AES();
          String text = enc.encrypt(message, key);
          out.write(text);
        }
        catch (IOException ioe) { error(ioe.getMessage());return false; }
      }
      else return false;
    }
    return true;
    '''
  </p>
  </details>
