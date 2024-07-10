**Welcome to Wherewego API Docs!**

## This page describes how to setup your local server env.

- This page also describes how to sync with origin developer's env.
- We are using MySQL server 5.7 and MySQL Workbench 8.0.
- Install MySQL in your host environment first.

## General: We decided to provide Jupyter Notebook on our project.

- Reference: [http://www.incodom.kr/Jupyter_in_Django](http://www.incodom.kr/Jupyter_in_Django)
- We listed django-extensions on "requirements.txt" so all you need is
    
    Put this command "pip install notebook" into your Venv prompt 
    
    Then you can use Jupyter Notebook on our project environment.
    
## First, Get your own **Miniconda**

- Our platform uses Django on Miniconda environment, so install your own Conda.
- Then, use "conda create —n [Your Virtual Env name] python=3.7" command to create a new virtual environment.
- Then, activate it! (by using "conda activate [Your Virtual Env name]")
- Then use command "cd [Your Folder Path]" to move your project folder.

- Origin Developer's Virtual Env (from now on, Venv) name is "wherewego".

## Second, Install Django on your Miniconda Env

- Just use "pip install Django" command then conda will do everything without disturbance.
- When you finished, you are ready to use Django!

- Other requirements will be described in "requirements.txt"
    
    And this page will tell you how to use it.
    
## Third. Shall we start the Django Project?

- In this project, you will clone the Origin developer's source code, so just clone it!
    
    BUT BE AWARE! You might not want to clone all files including the FrontEnd folder.
    
    It includes 1000+ files, so just clone the "Backend" folder only.
    
- Now, check out your "requirements.txt" file in your cloned folder.
    
    That file includes requirements to use our project. But, first, you must delete
    
    "Django2.2.-", "pytz". It is already installed in your Venv, so delete them first.
    
- Then use "pip install -r requirements.txt" command in your Venv prompt.

### BE AWARE!

- Some problems might occur when using requirements.txt file. In that case, use "conda install" instead of "pip install" for specific libraries.
- If you encounter errors with Django version compatibility, try installing the compatible versions as specified in the documentation.

## Using MySQL Server

- To connect your Django project to MySQL, update your settings.py file with the appropriate database configurations.
- Ensure MySQL server is running and accessible.

## Setting Up the Frontend

- The frontend part of the project uses React.js. Ensure you have Node.js installed.
- Navigate to the Frontend directory and run "npm install" to install all dependencies.
- Use "npm start" to launch the development server.

## Syncing with Origin Developer's Environment

- To keep your environment in sync with the origin developer's setup, follow the instructions provided in the synchronization guide.
- Regularly pull updates from the main repository to stay up-to-date with changes.

## Backend and Frontend Communication

- The backend communicates with the frontend through RESTful APIs.
- Ensure CORS is configured correctly in Django settings to allow frontend to communicate with the backend.

## Deployment

- For deploying the project, consider using services like Heroku, AWS, or DigitalOcean.
- Set up environment variables for production settings and secure your application accordingly.

## Project Overview

### Backend

1. The backend is built with Django and follows a modular structure.
2. Key functionalities include user authentication, data management, and API endpoints.

### Frontend

1. The frontend is built with React.js and provides a responsive user interface.
2. It interacts with the backend through API calls to fetch and display data.

### Database

1. The project uses MySQL for data storage.
2. Ensure you have the correct database schema set up by running migrations.

### Key Features

1. User authentication and authorization.
2. Data visualization using charts and graphs.
3. Integration with external APIs for enhanced functionality.

## Development Schedule

1. Backend development started on 3rd September 2019.
2. Frontend development was suspended until 15th September 2019 but will continue concurrently with backend development.
3. From 17th August 2019 to 2nd September 2019, focus was on developing the internal algorithm.

## Internal Algorithm Development

- Using TensorFlow and Pandas to manage and score data.
- Aim to complete or reach at least 50% of the algorithm development by 2nd September 2019.

## Current Status

1. Backend is not fully prepared, including modeling and design.
2. Frontend development was suspended after integrating Google API, which is functional now.
3. Crawler code in the "enhanced folder" is fully functional and excludes certain unwanted characters.

## Future Plans

- Continue backend and frontend development as per the schedule.
- Improve and finalize the internal algorithm for better data scoring and recommendations.

**Wrote on 17th August 2019**

### On Develop
