mkdir djangogirls
cd djangogirls

virtualenv -p python3 myvenv
source myvenv/bin/activate
--> deactivate  (in myvenv shell known command)

pip install django

django-admin startproject mysite .

vi mysite/settings.py  
-> TIME_ZONE = 'Europe/Berlin'
-> STATIC_URL = '/static/'
   STATIC_ROOT = os.path.join(BASE_DIR, 'static')

vi mysite/settings.py
   'blog',

vi blog/models.py 
->->

python manage.py makemigrations blog
python manage.py sqlmigrate blog 0001
python manage.py migrate

python manage.py createsuperuser
python manage.py runserver
http://127.0.0.1:8000/admin/




===============================================
https://docs.djangoproject.com/en/1.9/intro/

-------------------------------------------------
problem with datetime:

>>> p = Poll.objects.get(pk=1)
>>> p.was_published_recently()
True

but

models.py line 12 in was_published_recently
NameError: global name 'datetime' is not defined..

solution:
sudo pip install pytz


-------------------------------------------------
Tutorial and further links:
http://tutorial.djangogirls.org/en/django_orm/index.html
