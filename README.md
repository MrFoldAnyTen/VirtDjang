# VirtDjang
virtualenv implementation of django using python3


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
<br />
set timezone <br />
python manage.py migrate<br />
add installed app <br />
python manage.py makemigrations polls
<br />
(ENV) dylan@Malvin ~/temp/temp/temp/Django-Web-Page/ENV/mysite $ python manage.py makemigrations polls<br />
Migrations for 'polls':<br />
  polls/migrations/0001_initial.py:<br />
    - Create model Choice<br />
    - Create model Question<br />
    - Add field question to choice<br />
(ENV) dylan@Malvin ~/temp/temp/temp/Django-Web-Page/ENV/mysite $ <br />
<br />
python manage.py migrate<br />
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


python manage.py createsuperuser
