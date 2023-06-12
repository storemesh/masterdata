# Django Master data
0. install dsm-django-masterdata
```
pip install pip install dsm-django-masterdata
```
1. install django app in `settings.py`
```python
INSTALLED_APPS = [
    ...
    'dsm_django_masterdata.hscode',
    ...
]
```

2. migrate database
```
python manage.py migrate
```

3. check data in admin page

## How to use
```python
from dsm_master.hscode.models import HScode
hs_code = HScode.objects.all()
```