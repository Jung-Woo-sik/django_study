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
App의 트리를 보면 다음과 같다.
<pre><code>
app_name/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    views.py

</code></pre>

* view 작성
app에 views.py를 수정한다. 
<pre><code>
from django.http import HttpResponse


def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")

</code></pre>
코드를 작성한 후에 뷰를 호출하려면 URL을 연결해주어야 하는데 url을 연결하려면 app에있는 urls.py와 project에 있는 urls.py를 둘 다 수정해 주어야 한다.

* app urls.py
<pre><code>
from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]

</code></pre>

* project urls.py
<pre><code>
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]

</code></pre>
![Alt text](./img/view.png)
![Alt text](./img/view.png "django 기초 view")

