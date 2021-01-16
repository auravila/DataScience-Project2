

## Bank Marketing Forecast

The objective of this project is to train a model to forecast the likelihood of getting a loan determined by "y" attribute on the collected data (dataset) utilize 
automl and pipeline mechanism to determin the best mode, deploy and make it availale and interact with the it via deployed enpoints.

## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. An architectural diagram is an image that helps visualize the flow of operations from start to finish. In this case, it has to be related to the completed project, with its various stages that are critical to the overall flow. For example, one stage for managing models could be "using Automated ML to determine the best model". 

## Key Steps
The Following section describes a brief description on the lis of steps take to produce the automl pipeline project for the Bank Marketing dataset

Step1:
Load and register the marketing dataset, make sure it is a tabular dataset and first line include headers
![1](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/1-RegisteredDataset.png)

Step2:
Configure an automl experiment using the designer and the dataset from step1. Select the column y as the value to predict and set the model as classification
tune timeout parametersand concurrency runs in ordert to execute experiment
![2](https://github.com/auravila/DataScience-Project2/blob/master/Screenshots/2-ExperimentCompleted.jpeg)

Step3:
Identify best model for experiment, in this case Voting ensamble turned around to be the best algorithm with an accuracy metric of 0.918%
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

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
During this project there were a few tricky bits specially around getting docker up and running. Specially on a MAC OS, also a lot of time was spent trying to troublesshot issues with python libraries and compatiblity. The main issue was aroung getting picke and joblib to work. I discovered that in order to make this step to work I had to use the correct sdk verion 1.19.0
