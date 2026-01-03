# Burp Suite Professional Installation steps for Linux

Link - This version of the Burpsuite Works with the "Java 11" as some flags in the further commands may not work for the Java 17 or 21 

```bash  
Link="https://portswigger-cdn.net/burp/releases/download?product=pro&version=2022.8.2&type=jar"
```
# Intall Java 11 
```bash
sudo pacman -S jdk11-openjdk (Arch)

or

sudo apt install openjdk-11-jdk (Debian)

```

# execute Keygenerator
```bash
echo 'Starting Keygenerator'
(java -jar keygen.jar) & 
```
# Execute Burp Suite Professional with Keyloader
```bash 
echo "/usr/lib/jvm/java-11-openjdk/bin/java --illegal-access=permit -Dfile.encoding=utf-8 -javaagent:$(pwd)/loader.jar -noverify -jar $(pwd)/burpsuite_pro_v2022.8.2.jar &" > burp
chmod +x burp
cp burp /bin/burp 
(./burp) 
```


Burp Suite Pro Activation Steps
1. Modify License String like "license to Siddharth"
2. Copy License key from keygen.jar and paste in Burp Suite Pro and click Next.
3. Select Manual Activation Option on your bottom Right in Burp Suite Pro.
4. Copy License Request from BurpSuite_Pro and paste in Keygenerator.
5. Copy license response from Keygenerator and paste in Burp Suite Pro, then next and Done.
Executing Burp Suite Profession after Activation
--> Kali Linux :-: You can start Burp Suite Professional by writing **burp** in terminal.
Updating Burp Suite Professional
--> Replace existing Burp-Suite-Pro.jar file with latest Burp Suite Professional jar 
