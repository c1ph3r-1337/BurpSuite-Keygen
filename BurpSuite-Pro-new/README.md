# Burp Suite Professional Installation steps for Linux

> Link - Use this link to install newer Version of the BurpSuite

```bash
Link="https://portswigger-cdn.net/burp/releases"
```

# Execute Keygenerator

> Note - Both Keygen and BurpSuite jar File should be in same directory.

<br>

```bash
java -jar BurpLoaderKeygen_v1.18.jar &
```

or  

```bash
echo "java -jar $(pwd)/BurpLoaderKeygen_v1.18.jar &" > burp
chmod +x burp
cp burp /bin/burp 
(./burp) 
```
<br>

> **Burp Suite Pro Activation Steps**
> 1. Modify License String like "license to h3110w0r1d"
> 2. Copy License key from keygen.jar and paste in Burp Suite Pro and click Next.
> 3. Select Manual Activation Option on your bottom Right in Burp Suite Pro.
> 4. Copy License Request from BurpSuite_Pro and paste in Keygenerator.
> 5. Copy license response from Keygenerator and paste in Burp Suite Pro, then next and Done.

<br>

Credit - [h3110w0r1d](https://github.com/h3110w0r1d-y)
