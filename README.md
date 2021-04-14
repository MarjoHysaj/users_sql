# users_sql
(djangoPy3Env) C:\Users\Perdorues\Desktop\users_sql\users_sql>python manage.py shell
Python 3.9.2 (tags/v3.9.2:1a79785, Feb 19 2021, 13:44:55) [MSC v.1928 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
(InteractiveConsole)
>>> from users_app.models import *
>>> users = Users.objects.create(first_name="Mario",last_name="Hysaj",email_address="mariohysaj@gmail.com",age=22)
>>> users = Users.objects.create(first_name="Olsi",last_name="Hysaj",email_address="e3@gmail.com",age=23)
>>> users = Users.objects.create(first_name="Xhulio",last_name="Hoxha",email_address="xhulio@gmail.com",age=32)
>>> Users.objects.all()
<QuerySet [<Users: Users object (1)>, <Users: Users object (2)>, <Users: Users object (3)>]>
>>> Users.objects.last()
<Users: Users object (3)>
>>> Users.objects.first()
<Users: Users object (1)>
>>> updated_user = Users.objects.get(id=3)
>>> updated_user.last_name = "Pancake"
>>> updated_user.save()
>>> deleted_user = Users.objects.get(id=2)
>>> deleted_user.delete()
(1, {'users_app.Users': 1})
>>> Users.objects.all().values()
<QuerySet [{'id': 1, 'first_name': 'Mario', 'last_name': 'Hysaj', 'email_address': 'mariohysaj@gmail.com', 'age': 22, 'created_at': datetime.datetime(2021, 4, 14, 16, 48, 35, 553639, tzinfo=<UTC>), 'updated_at': datetime.datetime(2021, 4, 14, 16, 48, 35, 553639, tzinfo=<UTC>)}, {'id': 3, 'first_name': 'Xhulio', 'last_name': 'Pancake', 'email_address': 'xhulio@gmail.com', 'age': 32, 'created_at': datetime.datetime(2021, 4, 14, 16, 50, 50, 128150, tzinfo=<UTC>), 'updated_at': datetime.datetime(2021, 4, 14, 16, 59, 36, 652526, tzinfo=<UTC>)}]>
>>> Users.objects.all().order_by("first_name")
<QuerySet [<Users: Users object (1)>, <Users: Users object (3)>]>
>>> Users.objects.all().order_by("-first_name")
<QuerySet [<Users: Users object (3)>, <Users: Users object (1)>]>
