## 

```bash
darina@MacBook-Pro brute-force-server % mkdir keylogger
cd keylogger
touch main.py
darina@MacBook-Pro keylogger % cd ..
darina@MacBook-Pro brute-force-server % cd ..
darina@MacBook-Pro ~ % mkdir keylogger
darina@MacBook-Pro ~ % cd keylogger
darina@MacBook-Pro keylogger % touch main.py
darina@MacBook-Pro keylogger % pip install pynput
```

<details>
Defaulting to user installation because normal site-packages is not writeable
Collecting pynput
  Downloading pynput-1.8.2-py2.py3-none-any.whl.metadata (32 kB)
Collecting six (from pynput)
  Downloading six-1.17.0-py2.py3-none-any.whl.metadata (1.7 kB)
Collecting pyobjc-framework-ApplicationServices>=8.0 (from pynput)
  Downloading pyobjc_framework_applicationservices-12.2.2-cp312-cp312-macosx_10_13_universal2.whl.metadata (2.8 kB)
Collecting pyobjc-framework-Quartz>=8.0 (from pynput)
  Downloading pyobjc_framework_quartz-12.2.2-cp312-cp312-macosx_10_13_universal2.whl.metadata (3.6 kB)
Collecting pyobjc-core>=12.2.2 (from pyobjc-framework-ApplicationServices>=8.0->pynput)
  Downloading pyobjc_core-12.2.2-cp312-cp312-macosx_10_13_universal2.whl.metadata (2.8 kB)
Collecting pyobjc-framework-Cocoa>=12.2.2 (from pyobjc-framework-ApplicationServices>=8.0->pynput)
  Downloading pyobjc_framework_cocoa-12.2.2-cp312-cp312-macosx_10_13_universal2.whl.metadata (2.6 kB)
Collecting pyobjc-framework-CoreText>=12.2.2 (from pyobjc-framework-ApplicationServices>=8.0->pynput)
  Downloading pyobjc_framework_coretext-12.2.2-cp312-cp312-macosx_10_13_universal2.whl.metadata (2.8 kB)
Downloading pynput-1.8.2-py2.py3-none-any.whl (92 kB)
Downloading pyobjc_framework_applicationservices-12.2.2-cp312-cp312-macosx_10_13_universal2.whl (32 kB)
Downloading pyobjc_framework_quartz-12.2.2-cp312-cp312-macosx_10_13_universal2.whl (219 kB)
Downloading six-1.17.0-py2.py3-none-any.whl (11 kB)
Downloading pyobjc_core-12.2.2-cp312-cp312-macosx_10_13_universal2.whl (6.4 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.4/6.4 MB 769.1 kB/s eta 0:00:00
Downloading pyobjc_framework_cocoa-12.2.2-cp312-cp312-macosx_10_13_universal2.whl (388 kB)
Downloading pyobjc_framework_coretext-12.2.2-cp312-cp312-macosx_10_13_universal2.whl (30 kB)
Installing collected packages: six, pyobjc-core, pyobjc-framework-Cocoa, pyobjc-framework-Quartz, pyobjc-framework-CoreText, pyobjc-framework-ApplicationServices, pynput
Successfully installed pynput-1.8.2 pyobjc-core-12.2.2 pyobjc-framework-ApplicationServices-12.2.2 pyobjc-framework-Cocoa-12.2.2 pyobjc-framework-CoreText-12.2.2 pyobjc-framework-Quartz-12.2.2 six-1.17.0

[notice] A new release of pip is available: 24.2 -> 26.2.1
[notice] To update, run: pip install --upgrade pip
darina@MacBook-Pro keylogger % nano main.py
darina@MacBook-Pro keylogger % cd ~/keylogger && python3 main.py
Traceback (most recent call last):
  File "/Users/darina/keylogger/main.py", line 4, in <module>
    from pynput.keyboard import Key, Listener
ModuleNotFoundError: No module named 'pynput'
darina@MacBook-Pro keylogger % pip3 install pynput
Defaulting to user installation because normal site-packages is not writeable
Collecting pynput
  Using cached pynput-1.8.2-py2.py3-none-any.whl.metadata (32 kB)
Collecting six (from pynput)
  Using cached six-1.17.0-py2.py3-none-any.whl.metadata (1.7 kB)
Collecting pyobjc-framework-ApplicationServices>=8.0 (from pynput)
  Downloading pyobjc_framework_applicationservices-12.2.2-cp313-cp313-macosx_10_13_universal2.whl.metadata (2.8 kB)
Collecting pyobjc-framework-Quartz>=8.0 (from pynput)
  Downloading pyobjc_framework_quartz-12.2.2-cp313-cp313-macosx_10_13_universal2.whl.metadata (3.6 kB)
Collecting pyobjc-core>=12.2.2 (from pyobjc-framework-ApplicationServices>=8.0->pynput)
  Downloading pyobjc_core-12.2.2-cp313-cp313-macosx_10_13_universal2.whl.metadata (2.8 kB)
Collecting pyobjc-framework-Cocoa>=12.2.2 (from pyobjc-framework-ApplicationServices>=8.0->pynput)
  Downloading pyobjc_framework_cocoa-12.2.2-cp313-cp313-macosx_10_13_universal2.whl.metadata (2.6 kB)
Collecting pyobjc-framework-CoreText>=12.2.2 (from pyobjc-framework-ApplicationServices>=8.0->pynput)
  Downloading pyobjc_framework_coretext-12.2.2-cp313-cp313-macosx_10_13_universal2.whl.metadata (2.8 kB)
Using cached pynput-1.8.2-py2.py3-none-any.whl (92 kB)
Downloading pyobjc_framework_applicationservices-12.2.2-cp313-cp313-macosx_10_13_universal2.whl (32 kB)
Downloading pyobjc_framework_quartz-12.2.2-cp313-cp313-macosx_10_13_universal2.whl (219 kB)
Using cached six-1.17.0-py2.py3-none-any.whl (11 kB)
Downloading pyobjc_core-12.2.2-cp313-cp313-macosx_10_13_universal2.whl (6.4 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.4/6.4 MB 789.9 kB/s eta 0:00:00
Downloading pyobjc_framework_cocoa-12.2.2-cp313-cp313-macosx_10_13_universal2.whl (388 kB)
Downloading pyobjc_framework_coretext-12.2.2-cp313-cp313-macosx_10_13_universal2.whl (30 kB)
Installing collected packages: six, pyobjc-core, pyobjc-framework-Cocoa, pyobjc-framework-Quartz, pyobjc-framework-CoreText, pyobjc-framework-ApplicationServices, pynput
Successfully installed pynput-1.8.2 pyobjc-core-12.2.2 pyobjc-framework-ApplicationServices-12.2.2 pyobjc-framework-Cocoa-12.2.2 pyobjc-framework-CoreText-12.2.2 pyobjc-framework-Quartz-12.2.2 six-1.17.0

[notice] A new release of pip is available: 24.3.1 -> 26.2.1
[notice] To update, run: pip3 install --upgrade pip
</details>

```bash
darina@MacBook-Pro keylogger % cd ~/keylogger && python3 main.py
```
<details>
This process is not trusted! Input event monitoring will not be possible until it is added to accessibility clients.
Start key logging...
Key Pressed:  Key.cmd
Key Pressed:  Key.tab
Key Pressed:  'р'
рKey Pressed:  'у'
уKey Pressed:  'д'
дKey Pressed:  'д'
дKey Pressed:  Key.ctrl
Key Pressed:  Key.space
Key Pressed:  'f'
fKey Pressed:  'f'
fKey Pressed:  'f'
fEnd key logging...
darina@MacBook-Pro keylogger % cat ~/keylogger/log.txt       
рудд
darina@MacBook-Pro keylogger % pip3 install requests
Defaulting to user installation because normal site-packages is not writeable
Collecting requests
  Using cached requests-2.34.2-py3-none-any.whl.metadata (4.8 kB)
Collecting charset_normalizer<4,>=2 (from requests)
  Using cached charset_normalizer-3.5.2-cp313-cp313-macosx_10_13_universal2.whl.metadata (46 kB)
Collecting idna<4,>=2.5 (from requests)
  Using cached idna-3.20-py3-none-any.whl.metadata (7.2 kB)
Collecting urllib3<3,>=1.26 (from requests)
  Using cached urllib3-2.8.0-py3-none-any.whl.metadata (7.4 kB)
Collecting certifi>=2023.5.7 (from requests)
  Using cached certifi-2026.7.22-py3-none-any.whl.metadata (2.5 kB)
Using cached requests-2.34.2-py3-none-any.whl (73 kB)
Using cached certifi-2026.7.22-py3-none-any.whl (136 kB)
Using cached charset_normalizer-3.5.2-cp313-cp313-macosx_10_13_universal2.whl (366 kB)
Using cached idna-3.20-py3-none-any.whl (69 kB)
Using cached urllib3-2.8.0-py3-none-any.whl (135 kB)
Installing collected packages: urllib3, idna, charset_normalizer, certifi, requests
  WARNING: The script idna is installed in '/Users/darina/Library/Python/3.13/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
  WARNING: The script normalizer is installed in '/Users/darina/Library/Python/3.13/bin' which is not on PATH.
Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
Successfully installed certifi-2026.7.22 charset_normalizer-3.5.2 idna-3.20 requests-2.34.2 urllib3-2.8.0

[notice] A new release of pip is available: 24.3.1 -> 26.2.1
[notice] To update, run: pip3 install --upgrade pip
</details>

### second window

```bash
darina@MacBook-Pro ~ % cd ~/keylogger && rm log.txt 2>/dev/null; python3 main.py 
This process is not trusted! Input event monitoring will not be possible until it is added to accessibility clients.
Start key logging...
Key Pressed:  'в'
вKey Pressed:  'ф'
фKey Pressed:  'к'
кKey Pressed:  'ш'
шKey Pressed:  'т'
тKey Pressed:  'ф'
фKey Pressed:  Key.space
 Key Pressed:  Key.ctrl
Key Pressed:  Key.space
Key Pressed:  'b'
bKey Pressed:  'u'
uKey Pressed:  'r'
rKey Pressed:  'd'
dKey Pressed:  'y'
yKey Pressed:  'a'
aKey Pressed:  'e'
eKey Pressed:  'v'
vKey Pressed:  'a'
aKey Pressed:  Key.space
 Key Pressed:  'd'
dKey Pressed:  'a'
aKey Pressed:  'r'
rKey Pressed:  'i'
iKey Pressed:  'n'
nKey Pressed:  'a'
aEnd key logging...
Data sent to server. Response: "Invalid credentials"
darina@MacBook-Pro keylogger % вфкштф burdyaeva darina
```

### third window
```bash
darina@MacBook-Pro ~ % cd ~/brute-force-server && python3 -m uvicorn main:app --host localhost --port 8000
/Library/Frameworks/Python.framework/Versions/3.13/bin/python3: No module named uvicorn
darina@MacBook-Pro brute-force-server % pip3 install uvicorn
darina@MacBook-Pro brute-force-server % cd ..
darina@MacBook-Pro ~ % pip3 install uvicorn
pip install python-multipart
darina@MacBook-Pro brute-force-server % pip3 install python-multipart
Defaulting to user installation because normal site-packages is not writeable
Collecting python-multipart
Using cached python_multipart-0.0.32-py3-none-any.whl.metadata (2.1 kB)
Using cached python_multipart-0.0.32-py3-none-any.whl (30 kB)
Installing collected packages: python-multipart
Successfully installed python-multipart-0.0.32

[notice] A new release of pip is available: 24.3.1 -> 26.2.1
[notice] To update, run: pip3 install --upgrade pip
```

```bash
darina@MacBook-Pro brute-force-server % cd ~/brute-force-server && python3 -m uvicorn main:app --host localhost --port 8000
INFO:     Started server process [91945]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
INFO:     Uvicorn running on http://localhost:8000 (Press CTRL+C to quit)
INFO:     127.0.0.1:53653 - "POST /login HTTP/1.1" 200 OK
```
