# Configuring Jenkins Pipeline On AWS

This project involves provisioning an EC2 instance on Amazon Web Services (AWS), installing Jenkins, and building a Jenkins pipeline using Blue Ocean plugin. 


## Requirements

* An AWS user account. You may get one [here](https://aws.amazon.com/console/)

* A GitHub user account. Sign up [here](https://github.com/)

* Ubuntu 18.04 Operating System (OS)

* Jenkins 

* [Blue Ocean Plugin](https://www.jenkins.io/projects/blueocean/)

* AWS S3 Bucket

* HTML code

* Jenkins file



## Jenkins Setup

* Log into the [AWS Mangenment Console](https://aws.amazon.com/console/) with 
  your user name and password

* Launch a t2.micro EC2 instance with Unbuntu 18.04 selected as your OS. Follow 
  the guide [here](https://docs.aws.amazon.com/quickstarts/latest/vmlaunch/step-1-launch-instance.html)

* After launching an EC2 instance, 
  [remotely connect](https://docs.aws.amazon.com/quickstarts/latest/vmlaunch/step-2-connect-to-instance.html) to it. 

* Then [install Jenkins](https://www.jenkins.io/doc/book/installing/linux/#debianubuntu) on Ubuntu. 

* Now [unlock Jenkins](https://www.jenkins.io/doc/book/installing/linux/#setup-wizard) to create your administrator (Admin) user account, and install suggested plugins

* After installing the suggested plugins, log back into Jenkins with your Admin credentials. 

* Then install the [Blue Ocean plugin](https://www.jenkins.io/doc/book/blueocean/getting-started/#on-an-existing-jenkins-instance)


## Pipeline Setup

* [Create an S3 bucket](https://docs.aws.amazon.com/quickstarts/latest/s3backup/step-1-create-bucket.html) on AWS to store code artifact from the pipeline

* Log into your GitHub account and create a [repo](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/create-a-repo)

* [Create the above files](https://docs.github.com/en/free-pro-team@latest/github/managing-files-in-a-repository/creating-new-files) `index.html` and `Jenkins` with their respective content in your repo. 

* Modify the code in your `Jenkins` file to reflect your AWS Region and S3 bucket name

* Then [create a pipeline](https://www.jenkins.io/doc/book/blueocean/creating-pipelines/) using Blue Ocean with your GitHub repo 


## Pipeline Oveview

```
            GitHub ===> Lint HTML Code ===> S3 Bucket
```

So Jenkins creates a simple pipeline that pulls down HTML code from GitHub. Then lints the code for errors. If errors are found, Jenkins stops and reports back on why the pipeline fails. However, if no errors are found, Jenkins proceeds to upload the code to an S3 bucket. 


## License

The contents of this repository are covered under the [MIT Licence](#).