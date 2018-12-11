create django
mkdir djangogirls
cd djangogirls
python3 -m venv myvenv
python -m venv myvenv

myvenv\Scripts\activate

python3 -m pip install --upgrade pip

pip install django~=1.11.0 or python -m pip install django~=1.11.0
#это скрипт, который создаст необходимую структуру директорий и файлы для нас. Теперь у твоего проекта должна быть следующая структура:
django-admin.py

#внесём изменения в 
mysite/settings.py

TIME_ZONE = 'Europe/Moscow'
LANGUAGE_CODE = 'ru-ru'
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
ALLOWED_HOSTS = ['127.0.0.1', '<твоё_имя_пользователя>.pythonanywhere.com']
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'blog',
]

#Чтобы создать базу данных для блога
python manage.py migrate

#from root directory
python manage.py runserver or python manage.py runserver 0:8000
#open browser ==> http://127.0.0.1:8000/

#Создание приложения
python manage.py startapp blog
python manage.py makemigrations blog
python manage.py migrate blog

#сначала нужно создать суперпользователя 
python manage.py createsuperuser
#Username# walidatorkh@gmail.com
#Email address# walidatorkh@gmail.com
#Password# Odna_k0za