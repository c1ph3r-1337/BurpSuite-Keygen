#Link
''' Link="https://portswigger-cdn.net/burp/releases/download?product=pro&version=2022.8.2&type=jar" '''

# execute Keygenerator
''' 
echo 'Starting Keygenerator'
(java -jar keygen.jar) & 
'''

# Execute Burp Suite Professional with Keyloader
''' 
echo "java --illegal-access=permit -Dfile.encoding=utf-8 -javaagent:$(pwd)/loader.jar -noverify -jar $(pwd)/Burp_Suite_Pro.jar &" > burp
chmod +x burp
cp burp /bin/burp 
(./burp) 
'''
