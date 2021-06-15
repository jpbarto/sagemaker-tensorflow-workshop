# Amazon SageMaker - Tensorflow Workshop

The following is a small collection of labs related to using TensorFlow with Amazon SageMaker and automating the ML process using Apache Airflow.

## Prerequisites

**Access the Event Engine**

1. Visit https://dashboard.eventengine.run
1. Enter your event ID

**Create a SageMaker Notebook**

Using the [steps in the SageMaker documentation](https://docs.aws.amazon.com/sagemaker/latest/dg/gs-setup-working-env.html) create an Amazon SageMaker notebook.

1. Use an **Instance Type** of `ml.t3.large`
1. Have the notebook clone this Git repository.  Under **Git Repositories**, from the **Repository** drop down, select *Clone a git repository to this notebook only*.
1. Enter this Git repository url: `https://github.com/jpbarto/sagemaker-tensorflow-workshop.git`
1. After approximately 5 minutes the notebook will enter a state of `InService`, you can then access it using the `Open JupyterLab` link.

## Labs

### Lab 1: [Bring Your Own Container (with Tensorflow)](tensorflow_bring_your_own/tensorflow_bring_your_own.ipynb)
    
Using the linked Jupyter notebook above you will perform the following tasks:

1. Build a container hosting Tensorflow
1. Train a model locally with the container
1. Train a model in SageMaker with the container
1. Deploy the model in SageMaker with the container
1. Run inference against observations using the SageMaker API

### Lab 2: [Hyperparameter Optimization (with Tensorflow2)](tensorflow2_mnist/hpo_tensorflow2_mnist.ipynb)

Using the linked Jupyter notebook above you will perform the following tasks:

1. Define a training job using SageMaker-provided TensorFlow container
1. Use HPO to execute multiple training jobs in parallel to find the optimal model

### Lab 3: [Airflow Automation](https://amazon-mwaa-for-analytics.workshop.aws/en/workshop.html)

With the guidance of the linked lab materials below you will build an ML workflow with Apache Airflow and Amazon SageMaker.

1. Begin by [populating an Amazon S3 bucket](https://amazon-mwaa-for-analytics.workshop.aws/en/workshop/setup/s3.html) with data to be used by Apache Airflow.  
    > Note that the Amazon S3 Bucket has already been created for you.

1. Visit the [Managed Workflows for Apache Airflow console] (https://console.aws.amazon.com/mwaa/home?#environments)

1. Edit the Apache Airflow environment in order to specify the location of the `awsairflowlib.zip` and `requirements.txt` that were uploaded in the previous steps.

1. Under **Plugins file** use the **Browse S3** button to specify the `awsairflowlib.zip` file.

1. Under **Requirements file** use the **Browse S3** button to specify the `requirements.txt `file.

1. Click **Next** and then **Save** to complete the modification to the environment.

1. This will take up to 10 minutes to modify and reload the environment.  You can monitor the status of the environment using the [AWS console](https://console.aws.amazon.com/mwaa/home?#environments)

1. While the environment is updating create an IAM role for use by Amazon SageMaker.  Start by visiting the [AWS IAM console](https://console.aws.amazon.com/iam/home?#/roles).

1. Click **Create Role**

1. For role type, choose AWS Service, find and choose **SageMaker**, and choose **Next: Permissions**

1. On the Attach permissions policy page, choose (if not already selected)
    - AWS managed policy **AmazonSageMakerFullAccess**
    - AWS managed policy **AmazonS3FullAccess** for access to Amazon S3 resources

1. Then choose **Next: Tags** and then **Next: Review**.

1. For Role name, enter `AirflowSageMakerExecutionRole` and choose **Create Role**

1. The prerequisites are now complete.  Please use your [Cloud9 IDE](https://console.aws.amazon.com/cloud9/home) or local workstation to now complete the creation of an [Apache Airflow DAG](https://amazon-mwaa-for-analytics.workshop.aws/en/workshop/m3-ml-sagemaker.html).
