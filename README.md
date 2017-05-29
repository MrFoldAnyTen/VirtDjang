# VirtDjang<br />

# virtualenv implementation of django using python3<br />
<br />
https://docs.djangoproject.com/en/1.11/intro/tutorial02/<br />
<br />
virtualenv ENV  <br />
cd ENV  <br />
source bin/activate<br />
pip install django<br />
python -m django --version<br />
django-admin startproject mysite<br />
cd mysite<br />
python manage.py runserver<br />
python manage.py startapp polls<br />
<br />

# use github<br />
<br />
make github repository online<br />
git init<br />
git add .<br />
git commit -m "First commit"<br />
git remote add origin remote repository URL<br />
git remote -v<br />
git push origin master<br />
mrfoldanyten<br />
mr10<br />
<br />

# clone from github<br />
<br />
git clone https://github.com/MrFoldAnyTen/VirtDjang.git<br />
cd VirtDjang<br />
source bin/activate <br />
cd mysite<br />
atom .<br />
<br />
python manage.py runserver<br />add installed app <br />
Do some magik<br />
git add .<br />
git commit -m "more editing"<br />
git push origin master<br />
mrfoldanyten<br />
mr10<br />
<br />
<br />
set timezone <br />
LANGUAGE_CODE = 'en-uk'<br />
TIME_ZONE = 'Europe/London'<br />
add PollsConfig to INSTALLED_APPS<br />
python manage.py migrate<br />
python manage.py makemigrations polls<br />
<br />
    - Create model Choice<br />
    - Create model Question<br />
    - Add field question to choice<br />
(ENV) dylan@Malvin ~/temp/temp/temp/Django-Web-Page/ENV/mysite $ <br />
<br />
python manage.py sqlmigrate polls 0001<br />
python manage.py migrate<br />
<br />
change models, make migrations,migrate<br />
<br />

# Use the shell<br />
<br />

python manage.py shell<br />
<br />

>>> from polls.models import Question, Choice <br />
>>> Question.objects.all()<br />
>>> from django.utils import timezone<br />
>>> q = Question(question_text="What's new?", pub_date=timezone.now())<br />
>>> q.save()<br />
>>> q.id<br />
>>> q.question_text<br />
>>> q.pub_date<br />
>>> q.question_text = "What's up?"<br />
>>> q.save()<br />
>>> Question.objects.all()<br />

def __str__(self):<br />
It’s important to add __str__() methods to your models, <br />
for your own convenience when dealing with the interactive prompt<br />
and because objects’ representations are used throughout Django’s automatically-generated admin.<br />
<br />
>>> Question.objects.filter(id=1)
>>> Question.objects.filter(question_text__startswith='What')
>>> from django.utils import timezone
>>> current_year = timezone.now().year
>>> Question.objects.get(pub_date__year=current_year)
>>> Question.objects.get(id=2)
>>> Question.objects.get(id=2)  # primary key
>>> q = Question.objects.get(pk=1)
>>> q.was_published_recently()
>>> q = Question.objects.get(pk=1)
>>> q.choice_set.all()
>>> q.choice_set.create(choice_text='Not much', votes=0)
>>> q.choice_set.create(choice_text='The sky', votes=0)
>>> c = q.choice_set.create(choice_text='Just hacking again', votes=0)
>>> c.question
>>> q.choice_set.all()
>>> q.choice_set.count()
>>> Choice.objects.filter(question__pub_date__year=current_year)
>>> c = q.choice_set.filter(choice_text__startswith='Just hacking')
>>> c.delete()
<br />

## Creating an admin user <br />

# Creating an admin user <br />

## Creating an admin user <br />
### Creating an admin user <br />
just too seee what md works
# Creating an admin user <br />

python manage.py createsuperuser<br />
Username (leave blank to use 'sam'): admin<br />
Email address: admin@admin.com<br />
Password: mrfoldanyten<br />
Password (again): <br />
tell the admin that Question objects have an admin interface. <br />
creating the public interface<br />
<br />
<br />
<br />
<br />
<br />
<br />
