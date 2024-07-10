## This page describes how to setup your local server env.

- This page also describes how to sync with origin developer's env.
- we are using mysql server 5.7 and mysqlWorkbench 8.0
- install mysql in your host env first.

## General : We decided to provied JupyterNotebook on our project.

- reference : http://www.incodom.kr/Jupyter_in_Django
- We listed django-extensions on "requirements.txt" so all you need is
    
    put this command "pip install notebook" into your Venv prompt 
    
    Then you can use JupyterNotebook on our Project env.
    

## First, Get your own **Miniconda**

- Our platform uses Django on Miniconda env. so install your own Conda.
- Then, use "conda create —n [Your Virtual Env name] python=3.7" command to create new virtual Envrionment
- Then, activate it! (by using "conda activate [Your Virtual Env name]")
- Then use command "cd [Your Folder Path]" to move your project folder

- Origin Developer's Virtual Env (from now on, Venv) name is "wherewego"

## Second, Install Django on your Miniconda Env

- Just use "pip install Django" command then conda will do everything without disturbs.
- When you finished, you are ready to use Django!

- Other requirements will be described on "requirements.txt"
    
    And this page will tell you how to use it.
    

## Third. Shall we start Django Project?

- In this project, You will clone Origin developer's source code, so Just clone it!
    
    BUT BE AWARE! You might not want to clone all files including FrontEnd folder.
    
    It includes 1000+ files. so Just clone "Backend" folder only
    
- Now, checkout your "requirements.txt" file in your cloned folder
    
    That file include requirements to use our Project. But, first, you must delete
    
    "Django2.2.-", "pytz". It is already installed in your Venv. so delete them first
    
- then use "pip install -r requirements.txt" command in your Venv prompt.

### BEAWARE!

- Some problem has occured by using only requirements.txt
    
    which means, Venv has those listed pip things but localhost doesn't
    
    so if you encountered any "Import problem", try to manually install pip things
    
    which is listed in "localRequirements.txt". 
    
    Writing this page, I encountered "PyMysql import problem" So I added it in "localRequirements.txt"
    
    Please notice us any import problem occurs. Then We will add it to that txt
    

## Fourth. You gotta sync your Django Project with origin developer's

- First, Create your DB. By using command in mysql workbench "CREATE DATABASE [DB name] CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;"

     - By the way, Origin's DB name is wherewego

- Second, Ask "my_settings.py" file to your origin developer. That is Configure scheme File.
- Third, put "my_settings.py" which you got, into your project Folder. /'' -which is same location with "manage.py" file.- and modify that file following instructions in file.
- Fourth. use "py [manage.py](http://manage.py) migrate" in venv (conda propmt) then your DB will be sync-ed with developer's.

## Fifth. Shall we check our Django working hard?

- First, use command "py [manage.py](http://manage.py) runserver 0.0.0.0:8000" to run your server.
- If you worked properly, this results will be printed

```python
August 27, 2019 - 17:19:20
Django version 2.2.1, using settings 'wherewego.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.
```

- Open your IE, and Put URL "127.0.0.1:8000". And Press enter!
- Then you will see

!https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e72fbcaa-1046-49f1-9b22-48f57dfc4b6e/Reult1.jpg

- NOW, your Django is working hard.

## Sixth. Just read it please.

- DJango is a web framework which reacts other things' requests. So, local workset shouldn't be included in Django things.
- Now, you might wonder how to put your ".CSV" files in to project.
    
    Don't worry! Our kind Origin developer provides .py to put your .csv files into already existing models.
    
- But first, here is our Service model.

!https://s3-us-west-2.amazonaws.com/secure.notion-static.com/35421f56-1f7f-4370-9314-51b02118327e/_.jpg

1. Raw data which crawler crawled will be refined, and then Machine learning uses them as input data.
    
    After that, those results will be saved as a one file of ".csv" format.
    
2. Then, Those data will be put by "DBSynchronizer.py" which is created by origin developer.

A. Front end user inputs his/her location coordinates. then it will be sent to Backend server 

    as a format of coordinates or as a name of place.

B. Backend server accesses to DB to pull results 

C. It will be pulled following some instructions, formats

D. Our Backend Server returns thos results.

F. If resultset is coordinates, then we need to search those places

G. Then, some Search Engine returns results.

  - or, Front End can use it's own "googlemap API"

- And next, here is our Database table modeling

!https://s3-us-west-2.amazonaws.com/secure.notion-static.com/65a6e630-24f1-464d-81e6-756b319fb9f1/db2.jpg

- rawdata is raw data which Crawler got
- Dic is refined data which passed Machine Learning layers.

## Seventh. Let's put something into existing tables

- Our kind Origin developer added "DBSynchronizerTest.py" in folder "Backend".
    
    try that in Venv Propmt by using "python (or py or python3) DBSynchronizerTest.py"
    
    if you see this message, DB connection has created!
    

!https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ea7c6bc8-d980-4173-b8ee-658b2a1d631d/testdb1.jpg

## Eighth. Now, Put your .CSV infos into our Project DB!

WIP

tmr, need to do from .CSV to xlsx, and get in DB
