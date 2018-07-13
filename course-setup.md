---
layout: page
title: Deep Learning Course Setup
menu: true
---

## Setup:

The easiest way is to use Clouderizer and Google Colab.
Google Colab is a free service from Google to share and run code in the cloud, it also provides a GPU, which is necessary for deep learning.

Clouderizer is a cloud computing management service, it takes care of installing the required packages to a cloud computing instance (like Amazon AWS or in our case Google Colab).
Clouderizer is free for 200 hours per month and does not require a credit card, 

### 1. Registering the account:

[Get a Google Account](https://accounts.google.com/signup/v2/webcreateaccount?hl=en&flowName=GlifWebSignIn&flowEntry=SignUp) if you don't have one already and register for Clouderizer [here](https://console.clouderizer.com/auth/register)

Do **connect Clouderizer to Google Drive** when it asks after registration.

### 2. Create the project

Clone the template project like shown in the video below, making the same changes to the configuration. 

Make sure **not** to change the project name, otherwise the automatic data unpacking will not work.

<div>
 <video width="500" controls>
    <source src="/media/create_project.webm" type="video/webm">
</video>
</div>

Setup Script:

```bash
rclone copy clouderizer:clouderizer/Fast.ai/data /content/clouderizer/fast.ai/data
sleep 10
unzip "/content/clouderizer/fast.ai/data/*.zip" -d "/content/clouderizer/fast.ai/data/" > /dev/null
sleep 5
```


Startup Script: 

```bash 
----PRE TASK START----
pip install https://github.com/fastai/fastai/archive/master.zip
pip install torch torchvision
----PRE TASK END----

ln -s ~/clouderizer/fast.ai/data ~/clouderizer/fast.ai/fastai/courses/dl1/
jupyter nbextension enable --py widgetsnbextension --sys-prefix
```


### 3. Import the data

Copy the datasets from [my Google Drive](https://drive.google.com/open?id=1prPWEvYOS-HtDsrReIpkZLGYoRUOzzSW){:target="_blank"} into yours. 

* Select them all and select "Import into My Drive"
* Then move the files to the "clouderizer/Fast.ai/data" folder. 

Files in that Google Drive folder will be automatically downloaded to Colab, and .zip files will be unpacked.

<div>
 <video width="500" controls>
    <source src="/media/import_data.webm" type="video/webm">
</video>
</div>



### 4. Run the project

Note: Firefox sometimes gives an error when starting a Colab Notebook, for me changing to Chrome fixed it.

To run the project
* start a Colab Notebook
* set the runtime to Python 3 and enable GPU 
* go to the project at clouderizer and click run
* copy the command from the pop up
* paste it into colab, prepending a "!" (exclamation mark)
* execute the code

The initialization will take about 5-6 minutes, when it is finished you can connect to it via the project page from clouderizer (you might need to refresh that page).

<div>
 <video width="500" controls>
    <source src="/media/start.webm" type="video/webm">
</video>
</div>