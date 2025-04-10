# Production & Deployment
The steps required for this excersice

1. Train the model
2. Create web app using Flask
3. Commit the code in GitHub
4. Create an account in Heroku (PAAS)
5. Link the GitHub to Heroku
6. Deploy the model
7. Use the web app


After training in a .py file, because we want to make the model reusable, we use pickle to save the model. This is done by:

import pickle # the library required to save or dump the model

pickle.dump(trained_model, open('model.pkl','wb')) # Save the model to dist as model.pkl

This model will be deployed later, here in Heroku.

To create the web app: use github to just have the template code. 

https://github.com/krishnaik06/Heroku-Demo/blob/master/app.py

This reads the pickle file. once we load the model, we need a file like index.html as a webb app home page. Having the fields we need to do our prediction.

in the app.py file, @app.route('/') part, the slash renders the route page as the file index.html.

slash predict is a post method passing the model inputs to the model and bringing us the output. The output in the return line as prediction_text will be replaced in the html file in {{prediction_text}}.

finally we have a main function for running the whole flask.

Fpr running the code locally, just go to the file directory and run python3 app.py

you will get a local ip address. and you can use it locally.

Then we need to create the github repository. and for the deployment we need a configuration. This is the procfile. web: gunicorn app:app . The first app is the app.py file. the second app is flask app name in the app.py file. 

Then you need to create the requirements file. # creating the requirements file.
To create the requirement file of your project and knowing the version of libraries used in your projects and preventin… run: 

pip freeze >requirements.txt

This is very important. to have all the library names and their version.

This requirements should be ploaded in Heroku environments. 

Then upload the complete codes into github. commit the changes there.

Go to your Heroku profile. click new and create new app and give it a name. then click create app. then you should connect the github repository to this. search for your repository there. click connect. Then you should do automatic or manual deploy. Then click deploy branch. COngrats. the URL is ceated which can be used globally. click on view. and its there.