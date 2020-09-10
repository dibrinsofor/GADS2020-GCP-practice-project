## Lab Title: Getting Started with App Engine

## Objectives

In this lab, you learn how to launch a solution using Cloud Marketplace.

## First of all
1. In GCP console, on the top right toolbar, click the Open Cloud Shell button.

2. Click Continue and wait a few moments to provision and connect 

3. You can list the active account name with this command:

	 gcloud auth list 

4. You can list the project ID with this command:

	gcloud config list project 


## steps :

1. Use Cloud Marketplace to deploy a LAMP stack:

    -- take a look in resources existing in cloud Console.

    -- choose Marketplace from navigation menu

    -- search for 'LAMP'

    -- choose ' LAMP Certified by Bitnami '

    -- launch its page => set your nearby zone - leave the rest of settings as default
    
    -- deploy

2. Verify your deployment:

  --When the deployment is complete, click the Site address link.
  
  --open ssh of the deployment 
  
  --type:  cd /opt/bitnami (current working directory command)
    sudo sh -c 'echo "<?php phpinfo(); ?>" > apache2/htdocs/phpinfo.php'
    
  --exit ssh.
  
  --open a new tab and type : http://SITE_ADDRESS/phpinfo.php
    replace SITE_ADDRESS with the URL in the Site address field
    
## End Lab
