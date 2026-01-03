# Link - This version of the Burpsuite Works with the "Java 11" as some flags in the further commands may not work for the Java 17 or 21 

```bash  Link="https://portswigger-cdn.net/burp/releases/download?product=pro&version=2022.8.2&type=jar" ```

# execute Keygenerator
``` bash
echo 'Starting Keygenerator'
(java -jar keygen.jar) & 
```

# Execute Burp Suite Professional with Keyloader
```bash 
echo "java --illegal-access=permit -Dfile.encoding=utf-8 -javaagent:$(pwd)/loader.jar -noverify -jar $(pwd)/Burp_Suite_Pro.jar &" > burp
chmod +x burp
cp burp /bin/burp 
(./burp) 
```
