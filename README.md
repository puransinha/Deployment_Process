# Deployment_Process in different Platforms:

# Steps we are following to deploy our app on Heroku
    Step1: our main file name should be app.py
    Step2: Our Flask Instance name should be app
                app:app
    Step3: Create a new file and name it as Procfile
            Note: Procfile should not have any extension like .txt
                  P should be capital case

    Step4: In Procfile we are supposed to mention the commands which will be used by the cloud instance at the time of deployment

# Initialising the local GIT
    Step5: git init
    Step6: git add .
    Step7: git commit -m "Initial commit"

# Steps to Push Your Application from Local to Heroku Cloud
    Step8: heroku login
    Step9: heroku create
    Step10: git remote -v
    Step11: git push origin master

=================================++++++++++++++++++++++++++++++++++++++===========================================

# Steps we are following to deploy our app on AWS Elastic BeanStalk

    Step1: Your main python file name should be application.py
    Step2: Your flask object name, which we have defined in application.py should also be the application.
    Step3: .ebignore  is responsible to hold the name of those files which we don't want to push on a cloud.
    Step4: Create a requirements.txt file
            command : pip freeze > requirements.txt
    Step5: Create a folder in your application and name it as .ebextensions
    Step6: Inside .ebextensions we have to create a new file and name it as python.config
    Step7: In python.config we are suppose to mention the below commands
             option_settings:
                  "aws:elasticbeanstalk:container:python":
                    WSGIPath: application:application



=================================++++++++++++++++++++++++++++++++++++++===========================================
# Steps we are following to deploy our app on GCP

    Step1: Your main python file name should be main.py
    Step2: Your flask object name, which we have defined in application.py should also be the application.
    Step3: Create a new file and name is as app.yaml
    Step4: Add the belwo content to your app.yaml
            runtime: python
            env: flex
            entrypoint: gunicorn -b :$PORT main:application

            runtime_config:
              python_version: 3


            manual_scaling:
              instances: 1
            resources:
              cpu: 1
              memory_gb: 0.5
              disk_size_gb: 10

    Step5: Initialiase your local git using below command
            git init
