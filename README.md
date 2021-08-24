# django_study
## django 시작하기
1. 파이썬 설치
2. 장고 설치
<pre><code>
python -m pip install Django

</code></pre>
3. 설치 확인
<pre><code>
>>> import django
>>> print(django.get_version())
3.2
</code></pre>

## django project 만들기
1. project 생성
<pre><code>
python3 -m django startproject {project name}
</code></pre>
2. prject tree
<pre><code>
preject/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py
</code></pre>

* manage.py : 프로젝트와 상호작용하는 커맨드라인 유틸리
* settings.py : 프로젝트 환경 및 구성 저장
* urls.py : 프로젝트의 URL 선언 저장
* asgi.py : AGSI 웹서버의 엔트리포인트
* wsgi.py : WSGI 호환 웹 서버의 포인트

3. project 시작
<pre><code>
python3 manage.py runserver
</code></pre>
* App 만들기
<pre><code>
python3 manage.py startapp {app name}
</code></pre>


