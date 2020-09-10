## Lab Title: Getting Started with App Engine

## Objectives

In this lab, you learn how to perform the following tasks:

 - Initialize App Engine.

 - Preview an App Engine application running locally in Cloud Shell.

 - Deploy an App Engine application, so that others can reach it.

 - Disable an App Engine application, when you no longer want it to be visible.

## First of all
1. In GCP console, on the top right toolbar, click the Open Cloud Shell button.

2. Click Continue and wait a few moments to provision and connect 

3. You can list the active account name with this command:

	 gcloud auth list 

4. You can list the project ID with this command:

	gcloud config list project 


## Steps: 

1. Initialize App

    --Initialize your App Engine app with your project and choose its region:
        
        gcloud app create --project=$DEVSHELL_PROJECT_ID

    --Clone the source code repository for a sample application in the hello_world directory:
	
	    git clone https://github.com/GoogleCloudPlatform/python-docs-samples

    --Navigate to the source directory:
	
	    cd python-docs-samples/appengine/standard_python3/hello_world

2. Run Hello World application locally

    --Execute the following command to download and update the packages list:
	
	    sudo apt-get update

    --Set up a virtual environment in which you will run your application. Python virtual environments are used to isolate package installations from the system: 

	    sudo apt-get install virtualenv

		If prompted[Y/n],press Y and Enter
 
	    virtualenv -p python3 venv

    --Activate the virtual environment:
	
	    source venv/bin/activate 

    --Navigate to your project directory and install dependencies:

	    pip install  -r requirements.txt

    --Run the application: 

	    python main.py 


    --In Cloud Shell, click Web preview (Web Preview) > Preview on port 8080 to preview the application. 
	
    --Ctrl+C to abort the deployed service

    --Using the Cloud Console, verify that the app is not deployed using this command: 
	
	    gcloud app open-console

3. Deploy and runHello World on App Engine

    --Navigate to the source directory:

	    cd ~/python-docs-samples/appengine/standard_python3/hello_world

    --Deploy your Hello World application using this command: 

	    gcloud app deploy

		If prompted "Do you want to conitue(Y/n), press Y and then Enter. 

    --Launch your browser to view the app at http://YOUR_PROJECT_ID.appspot.com

	    gcloud app browse 

		click the URL

4. Disable the application, use this command:

    --List all versions of all services deployed to the App Engine server:
	
	    gcloud app versions list

    --You can now disable the version of any services deployed to the App Engine server: 

	    gcloud app versions stop --service=servicename v1 v2


## End your lab.