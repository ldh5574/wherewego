

# wherewego

## Our Project consists of Frontend(android) - Backend(Python_Django Web Framework) model.
  ### Our projects service modeling follows...
    1. A user puts the name of a place (e.g., "상암동") in the Frontend-App.
    2. Chooses one of his/her trip concepts, like "chilling or best restaurant".
    3. These infos will be transferred to Backend.
    4. Our Backend program finds places which are uploaded on Naver Blog posts:
       - This might be curious, why use Naver Blog posts?
         - A: Some companies, restaurants might pay for Ads, and we can't be sure of their infos or scores.
               But we can trust real reviews, and the easiest way to get those reviews is posts.
    5. Our Backend Program scores places and returns some places that got good scores.
       - Which means our project recommends places.
    6. Backend program returns places' coords, and Frontend will find places by that.

## Wrote on 17th Aug 2019

### On Develop.

## Here is our project develop schedule.

1. Backend Develop will start from 3rd Sep 2019.
2. Frontend Develop was suspended until 15th Sep 2019, but after that, it will start developing
   at the same time as backend developing.
3. From 17th Aug 19 to 2nd Sep 2019, We will develop our Internal Algorithm.

## Until now..

1. Backend isn't prepared at all including modeling, design for everything.
2. Frontend was suspended after importing google API, which is functional now.
3. In Source, Crawler code fully functional which is in "enhanced folder".
   - Also, this code excludes some \t, \^ sort of things.

## Why Back, Frontend development suspended?

  ***From 17th Aug 2019 to 2nd Sep 2019, we will develop our internal Algorithm.***
  - Which is scoring our results. 
    - If our Algorithm returns some name of restaurant, places, then it must be scored, which is good or not.
    - We are using TensorFlow, Pandas. 
    - It should be done or at least done by 50% until 2nd Sep 2019. So we will work on it.
    
## So, What will we going to do in developing internal algorithm?
  - Using TensorFlow or sort of things.
  - For now (17th Aug 2019), We are considering using pandas for manage our final data.
  - Constructing system flow.

---

**Welcome to Wherewego API Docs!**

## This page describes how to setup your local server env.

- This page also describes how to sync with origin developer's env.
- We are using mysql server 5.7 and mysqlWorkbench 8.0.
- Install mysql in your host env first.

## General: We decided to provide JupyterNotebook on our project.

- Reference: http://www.incodom.kr/Jupyter_in_Django
- We listed django-extensions on "requirements.txt" so all you need is
    put this command "pip install notebook" into your Venv prompt 
    Then you can use JupyterNotebook on our Project env.

## First, Get your own **Miniconda**

- Our platform uses Django on Miniconda env. so install your own Conda.
- Then, use "conda create —n [Your Virtual Env name] python=3.7" command to create a new virtual Environment.
- Then activate it! (by using "conda activate [Your Virtual Env name]")
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
    It includes 1000+ files. so Just clone "Backend" folder only.
- Now, checkout your "requirements.txt" file in your cloned folder.
    That file includes requirements to use our Project. But, first, you must delete
    "Django2.2.-", "pytz". It is already installed in your Venv. so delete them first.
- Then use "pip install -r requirements.txt" command in your Venv prompt.

### BEWARE!

- Some problem has occurred by using only requirements.txt
    Which means, Venv has those listed pip things but localhost doesn't
    So if you encountered any "Import problem", try to manually install pip things
    which are listed in "localRequirements.txt". 
    Writing this page, I encountered "PyMysql import problem" So I added it in "localRequirements.txt"
    Please notice us any import problem occurs. Then We will add it to that txt.

## Fourth. You gotta sync your Django Project with origin developer's

- First, Create your DB. By using command in mysql workbench "CREATE DATABASE [DB name] CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;"
     - By the way, Origin's DB name is wherewego.
- Second, Ask "my_settings.py" file to your origin developer. That is Configure scheme File.
- Third, put "my_settings.py" which you got, into your project Folder. /'' -which is same location with "manage.py" file.- and modify that file following instructions in file.
- Fourth. use "py [manage.py](http://manage.py) migrate" in venv (conda prompt) then your DB will be synced with developer's.

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
![image](https://github.com/ldh5574/wherewego/assets/46510929/b725ff5d-a987-4a27-a857-5a2a6895729b)

- NOW, your Django is working hard.

## Sixth. Just read it please.

- Django is a web framework which reacts to other things' requests. So, local workset shouldn't be included in Django things.
- Now, you might wonder how to put your ".CSV" files into the project.
    Don't worry! Our kind Origin developer provides .py to put your .csv files into already existing models.
    But first, here is our Service model.

![image](https://github.com/ldh5574/wherewego/assets/46510929/345dc273-f08e-478c-950c-332ad1d27242)


1. Raw data which crawler crawled will be refined, and then Machine learning uses them as input data.
    After that, those results will be saved as one file of ".csv" format.
2. Then, Those data will be put by "DBSynchronizer.py" which is created by origin developer.

A. Front end user inputs his/her location coordinates. then it will be sent to Backend server 
    as a format of coordinates or as a name of place.

B. Backend server accesses to DB to pull results.

C. It will be pulled following some instructions, formats.

D. Our Backend Server returns those results.

F. If resultset is coordinates, then we need to search those places.

G. Then, some Search Engine returns results.
  - or, Front End can use its own "googlemap API".

- And next, here is our Database table modeling.

![image](https://github.com/ldh5574/wherewego/assets/46510929/1e56405b-cf11-4c40-98d1-f5f3a988e300)


- rawdata is raw data which Crawler got.
- Dic is refined data which passed Machine Learning layers.

## Seventh. Let's put something into existing tables.

- Our kind Origin developer added "DBSynchronizerTest.py" in the folder "Backend".
    try that in Venv Prompt by using "python (or py or python3) DBSynchronizerTest.py"
    if you see this message, DB connection has been created!

![image](https://github.com/ldh5574/wherewego/assets/46510929/3650bcf0-ee75-4aba-af0a-50d26c97e5b2)


## Eighth. Now, Put your .CSV infos into our Project DB!

WIP
tmr, need to do from .CSV to xlsx, and get in DB

