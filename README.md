

## Bank Marketing Forecast

The objective of this project is to train a model to forecast the likelihood of getting a loan determined by "y" attribute on the collected data (dataset). Utilize 
automl and pipeline approaches to determine the best run, deploy the best model and make it available for interaction via the deployment of endpoints.

## Architectural Diagram
The High level solution designs image below shows two possible paths to forecats the likelihood of detemining the "y" attribute, both of the solutions are supported by compute instances. The first compute instances is required to run basic activities like configuring automls and running the jupyter notebook. The second compute "cluster compute" performs the heavy lifting of running the automl and pipeline automl activities.

The purpose of this diagram is to provide a contextual HLSD and not a details deep dive.

AzureML High Level Solution Design steps:
1- Load / make reference to the model dataset, i.e. Bank Marketing.csv
2- AzureML: Use the AzureML Designer to configure the automl model. (for this particular case a classification model)
3- Run the Experiment created by the AzureML Model
4- Determine the best run and identify the best model for deployment
5- Enable endpoints, REST urls for user consumption.

AutoML Pipeline High Level Solution Design steps:
1- Load / make reference to the model dataset, i.e. Bank Marketing.csv
2- Using a Jupyter notebook, programatically create the steps necessary to configure, train and run the automl pipeline
3- Programatically (Jupyter Notebook) identify the best run, best model and enable pipeline endpoints for user consumption.

![Arq](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/ArchitectureDiagram.jpeg)

## Key Steps
The Following section describes a brief description on the list of steps taken to produce the automl pipeline project for the Bank Marketing dataset

Step1:
Load and register the marketing dataset, make sure it is a tabular dataset and first line include headers
![1](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/1-RegisteredDataset.png)

Step2:
Configure an automl experiment using the designer and the dataset from step1. Select the column y as the value to predict and set the model as classification.
Set timeout parameter sand concurrency runs in ordert to execute experiment
![2](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/2-ExperimentCompleted.jpeg)

Step3:
Identify best model for experiment, in this case Voting ensamble turned to be the best algorithm with an accuracy metric of 0.918%
![3](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/3-BestModel.jpeg)

Step4:
Enble Application Insight by running logs py script
![4](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/4-InsightsEnabled.jpeg)

Step5:
Execution results of logs.py
![5](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/5-logs_py.jpeg)

Step6:
Swagger bash script and server py execution logs

![6](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/6.1-Swaggerandserverpyrun.jpeg)

Swagger API documentation and swagger model data input
![6.1](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/6.2-SwaggerAPI.jpeg)

Update to Swagger input json variables to run the deployed model
![6.2](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/6.3-SwaggerAPI2.jpeg)

Step7:
Results of calling the model via endpoint.py script
![7](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/7-Endpoint_py.jpeg)

Step8:
Using Apache benchmark to identify key benchmark values related to endpoint usage
![8](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/8-Benchmark.jpeg)

Step9:
Pipelines Executions from Jupyter notebook
![9](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/9-PipelinesCreatedandExecuted.jpeg)

Step10:
Run1 and Run11 list the previous execution of the model via AzureMl designer.
![10](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/11-BankDSAzureMLRun.jpeg)

Step11:
Pipeline endpoints create via Jupyter notebook
![11](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/12-PipelineSectionShowingEndpoints.jpeg)

Step12:
Published pipeline restpoint
![12](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/13-PublishedPipelineoverview.jpeg)

Step13:
Azureml widgets evidence of a successful pipeline completion
![13](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/14-WidgetsSteprun.jpeg)

Step13:
Pipeline Execution and REST point API Call

![14](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/15-PipelineExecution.jpeg)


Run 49 describe the Completed Experiment run and the Restpoint Call

![15](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/16-RestpointCall.jpeg)

## Screen Recording
https://youtu.be/7AU60QKXJ0M

## Standout Suggestions
During this project there were a few tricky bits specially around getting docker up and running. Specially on a MAC OS, also a lot of time was spent trying to troublesshot issues with python libraries and compatiblity. The main issue was aroung getting picke and joblib to work. I discovered that in order to make this step to work I had to use the correct sdk verion 1.19.0

I can also conclude by looking at the metrics that both runs generated similar results regarding classification metrics.

How to Improve the project in the future?

I would like to implement the following two approaches to validate the model's results

1- Run the model with less variables and features in order to see if I can obtain the same accuracy and reduce the risk of over-fitting.


2- Using more data will also help me with over-fitting and it will be more difficult for the model to memorize patterns.
