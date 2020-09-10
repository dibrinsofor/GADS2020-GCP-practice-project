## Lab Title : Getting Started with Compute Engine

## Objectives

## In this lab, you will learn how to perform the following tasks:

    Create a Compute Engine virtual machine using the Google Cloud Platform (GCP) Console.

    Create a Compute Engine virtual machine using the gcloud command-line interface.

    Connect between the two instances.


## First of all
1. In GCP console, on the top right toolbar, click the Open Cloud Shell button.

2. Click Continue and wait a few moments to provision and connect 

3. You can list the active account name with this command:

	 gcloud auth list 

4. You can list the project ID with this command:

	gcloud config list project 


## Steps

1. Create a virtual machine using the GCP Console


        gcloud compute instances create my-vm-1 --zone=us-central1-a --machine-type=n1-standard-1 --subnet=default --tags=http-server --image=debian-9-stretch-9v2020002

        gcloud compute firewall-rules create my-vm-1 --direction=INGRESS --network=default --action=ALLOW --rules=tcp:80 --source-ranges=0.0.0.0/0 --target-tags=http-server

2. Create a virtual machine using the gcloud command line
    setting the compute zone
        gcloud config set compute/zone us-central1-b
    creating vm instance 'my-vm-2'    
        gcloud compute instances create "my-vm-2" --machine-type "n1-standard-1" --image-project "debian-cloud" --image "debian-9-stretch-9v2020002" --subnet "default"

3. Connect between VM instances

    gcloud compute SSH my-vm-2

    --Use the ping command to confirm that my-vm-2 can reach my-vm-1 over the network:
        ping my-vm-1

    --Use the ssh command to open a command prompt on my-vm-1:
        ssh my-vm-1

    --At the command prompt on my-vm-1, install the Nginx web server:
        sudo apt-get install nginx-light -y

    --Use the nano text editor to add a custom message to the home page of the web server:
        sudo nano /var/www/html/index.nginx-debian.html

    --Add text like this, and replace YOUR_NAME with your name:
        Hi from JohnDe

    --Confirm that the web server is serving your new page:
        curl http://localhost/

        exit

    --To confirm that my-vm-2 can reach the web server on my-vm-1:
        curl http://my-vm-1/

    --Copy the External IP address for my-vm-1 and paste it into the address bar of a new browser tab.

## End your lab
