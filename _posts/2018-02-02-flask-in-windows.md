---
layout: post
---

## Working with Flask in Windows using Anaconda

1. Install Anaconda

2. Run Anaconda Prompt

3. Create git repository and clone it. Let's we have repository named `microblog`.

4. Change directory:

```
cd microblog
```

5. Create new virtual environment:

```
(base) C:\Users\Slava\microblog>conda create -n venv
Solving environment: done

## Package Plan ##

  environment location: C:\Users\Slava\Anaconda3\envs\venv


Proceed ([y]/n)? y

Preparing transaction: done
Verifying transaction: done
Executing transaction: done
#
# To activate this environment, use
#
#     $ conda activate venv
#
# To deactivate an active environment, use
#
#     $ conda deactivate
```

6. Activate virtual environment:
```
(base) C:\Users\Slava\microblog>conda activate venv
```

7. Install flask. In my Anaconda it's pre-installed:
```
(venv) C:\Users\Slava\microblog>pip install flask
Requirement already satisfied: flask in c:\users\slava\anaconda3\lib\site-packag
es
Requirement already satisfied: Werkzeug>=0.7 in c:\users\slava\anaconda3\lib\sit
e-packages (from flask)
Requirement already satisfied: Jinja2>=2.4 in c:\users\slava\anaconda3\lib\site-
packages (from flask)
Requirement already satisfied: itsdangerous>=0.21 in c:\users\slava\anaconda3\li
b\site-packages (from flask)
Requirement already satisfied: click>=2.0 in c:\users\slava\anaconda3\lib\site-p
ackages (from flask)
Requirement already satisfied: MarkupSafe>=0.23 in c:\users\slava\anaconda3\lib\
site-packages (from Jinja2>=2.4->flask)
```



