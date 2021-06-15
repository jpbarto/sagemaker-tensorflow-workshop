# sagemaker-tensorflow-workshop
A collection of labs related to using TensorFlow with Amazon SageMaker and automating the ML process using Apache Airflow.

1. [Bring Your Own Container (with Tensorflow)](https://github.com/aws/amazon-sagemaker-examples/blob/master/advanced_functionality/tensorflow_bring_your_own/tensorflow_bring_your_own.ipynb)
    1. Build a container hosting Tensorflow
    1. Train a model locally with the container
    1. Train a model in SageMaker with the container
    1. Deploy the model in SageMaker with the container
    1. Run inference against observations using the SageMaker API
1. [Hyperparameter Optimization (with Tensorflow2)](https://github.com/aws/amazon-sagemaker-examples/blob/master/hyperparameter_tuning/tensorflow2_mnist/hpo_tensorflow2_mnist.ipynb)
    1. Define a training job using SageMaker-provided TensorFlow container
    1. Use HPO to execute multiple training jobs in parallel to find the optimal model
1. [Airflow Automation](https://amazon-mwaa-for-analytics.workshop.aws/en/workshop.html)
    1. Building an ML workflow with Airflow and SageMaker

