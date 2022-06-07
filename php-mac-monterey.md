https://wpbeaches.com/updating-to-php-versions-7-4-and-8-on-macos-12-monterey/

Ref - https://www.simplified.guide/macos/keychain-ca-code-signing-create
Certificate Authority for Code Signing in macOS
Launch Keychain Access.
Go to Keychain Access → Certificate Assistant → Create a Certificate Authority from the menu bar.
Set a name for your CA.-> Ex- "Nikhilesh Patve CA"
Click on User Certificate select list.
Select Code Signing from the list.
Check on Let me override defaults checkbox.
Enter the email address for your CA. -> Ex - nikhilesh.patve@gmail.com
Click on Continue.
Accept defaults for Certificate Information and click Continue.
Enter certificate information and click Continue.
Accept defaults for Key Pair Information For This CA and click Continue.
Accept defaults for Key Pair Information For Users of This CA and click Continue.
Accept defaults for Key Usage Extensions For This CA and click Continue.
Accept defaults for Key Usage Extensions For Users of This CA and click Continue.
Click on Include Extended Key Usage Extension.
Click to check the Code Signing checkbox.
Click Continue.
Accept defaults for Extended Key Usage Extensions For Users of This CA and click Continue.
Accept defaults for Basic Constraints Extension For This CA and click Continue.
Accept defaults for Basic Constraints Extension For Users of This CA and click Continue.
Accept defaults for Subject Alternative Name For This CA and click Continue.
Accept defaults for Subject Alternative Name for Users of This CA and click Continue.
Click Create to create the CA.
Close the Certificate Assistant window and open Keychain Access.
Double click on your newly created CA in login → My Certificates.
Click on Trust.
Click on When using this certificate select list.
Click on Always trust.
Close the CA information window.
Authenticate to the system to enable your changes.


https://www.simplified.guide/macos/keychain-cert-code-signing-create
Code signing certificate in macOS
Launch Keychain Access.
Go to Keychain Access → Certificate Assistant → Create a Certificate from the menu bar.
Set the name of the certificate. Ex - "Nikhilesh Patve"
Click on Identity Type select list.
Select Leaf from the list.
Click on Certificate Type select list.
Select Code Signing from the list.
Click Create to continue.
Select CA or issuer from the list and click Create.
Click Done to finish the process.


https://www.simplified.guide/macos/apache-php-homebrew-codesign
Run on Terminal
>codesign --sign "Nikhilesh Patve Php" --force --keychain ~/Library/Keychains/login.keychain-db /usr/local/opt/php@7.4/lib/httpd/modules/libphp7.so
Update file /etc/apache2/other/00-httpd.conf
LoadModule php7_module /opt/homebrew/opt/php@7.4/lib/httpd/modules/libphp7.so "Nikhilesh Patve"
sudo apachectl -k restart
