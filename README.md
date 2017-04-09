python3 -m venv {my_env_name}
source {my_env_name}/bin/activate
my_env_name# > pip install django==1.8
my_env_name# > django-admin startproject mysite .
# django-admin.py 
# djangogirls
#├───manage.py
#└───mysite
#       settings.py
#       urls.py
#       wsgi.py
#       __init__.py
# manage.py 파일 또한 스크립트인데, 사이트 관리를 도와주는 역할을 이 스크립트로 다른 설치 작업 없이, 컴퓨터에서 웹 서버를 시작
# settings.py는 웹사이트 설정
# urls.py 파일은 urlresolver가 사용하는 패턴 목록을 포함하고 있다.
# 
# -----------------------------------------------------
# setup change
# -----------------------------------------------------
# mysite/settings.py을
# TIME_ZONE = 'Asia/Seoul'
# STATIC_URL = '/static/'
# STATIC_ROOT = os.path.join(BASE_DIR, 'static')
# db confirm
#     DATABASES = {
#       'default': {
#         'ENGINE': 'django.db.backends.sqlite3',
#         'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
#       }
#     }
python manage.py migrate
python manage.py runserver
# django server willbe appeared

python manage.py startapp blog

# insert blog into ISTALLED_APPS array in mysite/settings.py
# INSTALLED_APPS = ( 
#    'django.contrib.admin',
#    'django.contrib.auth',
#    'django.contrib.contenttypes',
#    'django.contrib.sessions',
#    'django.contrib.messages',
#    'django.contrib.staticfiles',
#    'blog',
#)
#blog/models.py writing

python manage.py makemigrations blog
#blog/admin.py change
python manage.py runserver

python manage.py createsuperuser


deployment

https://git-scm.com/

$ git init
#Initialized empty Git repository in ~/djangogirls/.git/
$ git config --global user.name "Your Name"
$ git config --global user.email you@example.com

vi .gitignore 
#*.pyc
#__pycache__
#myEnvDJ
#db.sqlite3
#.DS_Store
