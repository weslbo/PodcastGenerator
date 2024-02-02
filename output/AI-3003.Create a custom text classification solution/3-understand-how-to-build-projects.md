
# 
# Understand how to build text classification projects

Custom text classification projects are your workspace to build, train, improve, and deploy your classification model. You can work with your project in two ways: through **Language Studio** and via the REST API. Language Studio is the GUI that will be used in the lab, but the REST API has the same functionality. Regardless of which method you prefer, the steps for developing your model are the same.

## 
# Azure AI Language project life cycle

[![Diagram that shows a life cycle with steps to define labels, tag data, train model, view model, improve model, deploy model, and classify text.](../../wwl-data-ai/custom-text-classification/media/classify-development-lifecycle-small.png)](../../wwl-data-ai/custom-text-classification/media/classify-development-lifecycle.png#lightbox)

- - Define labels: Understanding the data you want to classify, identify the possible labels you want to categorize into. In our video game example, our labels would be "Action", "Adventure", "Strategy", and so on.
- - Tag data: Tag, or label, your existing data, specifying the label or labels each file falls under. Labeling data is important since it's how your model will learn how to classify future files. Best practice is to have clear differences between labels to avoid ambiguity, and provide good examples of each label for the model to learn from. For example, we'd label the game "Quest for the Mine Brush" as "Adventure", and "Flight Trainer" as "Action".
- - Train model: Train your model with the labeled data. Training will teach our model what types of video game summaries should be labeled which genre.
- - View model: After your model is trained, view the results of the model. Your model is scored between 0 and 1, based on the precision and recall of the data tested. Take note of which genre didn't perform well.
- - Improve model: Improve your model by seeing which classifications failed to evaluate to the right label, see your label distribution, and find out what data to add to improve performance. For example, you might find your model mixes up "Adventure" and "Strategy" games. Try to find more examples of each label to add to your dataset for retraining your model.
- - Deploy model: Once your model performs as desired, deploy your model to make it available via the API. Your model might be named "GameGenres", and once deployed can be used to classify game summaries.
- - Classify text: Use your model for classifying text. The lab covers how to use the API, and you can view the API reference

## 
# How to split datasets for training

When labeling your data, you can specify which dataset you want each file to be:

- - Training - The training dataset is used to actually train the model; the data and labels provided are fed into the machine learning algorithm to teach your model what data should be classified to which label. The training dataset will be the larger of the two datasets, recommended to be about 80% of your labeled data.
- - Testing - The testing dataset is labeled data used to verify you model after it's trained. Azure will take the data in the testing dataset, submit it to the model, and compare the output to how you labeled your data to determine how well the model performed. The result of that comparison is how your model gets scored and helps you know how to improve your predictive performance.

During the **Train model** step, there are two options for how to train your model.

- - Automatic split - Azure takes all of your data, splits it into the specified percentages randomly, and applies them in training the model. This option is best when you have a larger dataset, data is naturally more consistent, or the distribution of your data extensively covers your classes.
- - Manual split - Manually specify which files should be in each dataset. When you submit the training job, the Azure AI Language service will tell you the split of the dataset and the distribution. This split is best used with smaller datasets to ensure the correct distribution of classes and variation in data are present to correctly train your model.

To use the automatic split, put all files into the *training* dataset when labeling your data (this option is the default). To use the manual split, specify which files should be in testing versus training during the labeling of your data.

## 
# Deployment options

Azure AI Language allows each project to create both multiple models and multiple deployments, each with their own unique name. Benefits include ability to:

- - Test two models side by side
- - Compare how the split of datasets impact performance
- - Deploy multiple versions of your model

Note

Each project has a limit of ten deployment names

During deployment you can choose the name for the deployed model, which can then be selected when submitting a classification task:

## 
# Using the REST API

The REST API available for the Azure AI Language service allows for CLI development of Azure AI Language projects in the same way that Language Studio provides a user interface for building projects. Language Studio is explored further in this module's lab.

### 
# Pattern of using the API

The API for the Azure AI Language service operates asynchronously for most calls. In each step we submit a request to the service first, then check back with the service via a subsequent call to get the status or result.

With each request, a header is required to authenticate your request:

| Key | Value |
| --- | --- |
|  | The key to your Azure AI Language resource |

#### 
# Submit initial request

The URL to submit the request to varies on which step you are on, but all are prefixed with the endpoint provided by your Azure AI Language resource.

For example, to train a model, you would create a **POST** to the URL that would look something like the following:

| Placeholder | Value | Example |
| --- | --- | --- |
|  | The endpoint for your API request |  |
|  | The name for your project (value is case-sensitive) |  |

The following body would be attached to the request:

| Key | Value |
| --- | --- |
|  | Your model name. |
|  | The model version to use to train your model. |
|  | Boolean value to run validation on the test set. |
|  | Specifies evaluation options. |
|  | Specifies data split type. Can be if you're using an automatic split, or if you manually split your dataset |
|  | Required integer field only if is *percentage*. Specifies testing split. |
|  | Required integer field only if is *percentage*. Specifies training split. |

The response to the above request will be a , meaning the request was successful. Grab the value from the response headers, which will look similar to the following URL:

| Key | Value |
| --- | --- |
|  | Identifier for your request |

This URL is used in the next step to get the training status.

#### 
# Get training status

To get the training status, use the URL from the header of the request response to submit a **GET** request, with same header that provides our Azure AI Language service key for authentication. The response body will be similar to the following JSON:

Training a model can take some time, so periodically check back at this status URL until the response returns . Once the training has succeeded, you can view, verify, and deploy your model.

### 
# Consuming a deployed model

Using the model to classify text follows the same pattern as outlined above, with a POST request submitting the job and a GET request to retrieve the results.

#### 
# Submit text for classification

To use your model, submit a **POST** to the *analyze* endpoint at the following URL:

| Placeholder | Value | Example |
| --- | --- | --- |
|  | The endpoint for your API request |  |

Important

Remember to include your resource key in the header for 

The following JSON structure would be attached to the request:

| Key | Value |
| --- | --- |
|  | Which task you're requesting. The task is for multiple label projects, or for single label projects |
|  | The language code such as . |
|  | Your task name. |
|  | Your project name. |
|  | Your deployment name. |

The response to the above request will be a , meaning the request was successful. Look for the value in the response headers, which will look something like the following URL:

| Key | Value |
| --- | --- |
|  | The endpoint for your API request |
|  | Identifier for your request |

This URL is used to get your task results.

#### 
# Get classification results

Submit a **GET** request to the endpoint from the previous request, with the same header for authentication. The response body will be similar to the following JSON:

The classification result is within the items array's object, for each document submitted.

[Continue](/en-us/)

