
# 
# Define custom translations

While the default translation model used by Azure AI Translator is effective for general translation, you may need to develop a translation solution for businesses or industries in that have specific vocabularies of terms that require custom translation.

To solve this problem, you can create a custom model that maps your own sets of source and target terms for translation. To create a custom model, use the Custom Translator portal to:

1. [Create a workspace](/en-us/azure/ai-services/translator/custom-translator/quickstart) linked to your Azure AI Translator resource.
2. [Create a project](/en-us/azure/ai-services/translator/custom-translator/quickstart).
3. [Upload training data files](/en-us/azure/ai-services/translator/custom-translator/quickstart) and [train a model](/en-us/azure/ai-services/translator/custom-translator/quickstart).
4. [Test your model](/en-us/azure/ai-services/translator/custom-translator/quickstart) and [publish your model](/en-us/azure/ai-services/translator/custom-translator/quickstart).
5. Make translation calls to the API.

[![Screenshot showing the Custom Translator portal.](../../wwl-data-ai/translate-text-with-translator-service/media/custom-translator-new-small.png)](../../wwl-data-ai/translate-text-with-translator-service/media/custom-translator-new.png#lightbox)

Your custom model is assigned a unique **category Id** (highlighted in the screenshot), which you can specify in **translate** calls to your Azure AI Translator resource by using the **category** parameter, causing translation to be performed by your custom model instead of the default model.

## 
# How to call the API

To initiate a translation, you send a **POST** request to the following request URL:

Your request needs to include a couple of parameters:

- : The required version of the API.
- : The target language to translate to. For example: for French.
- : Your **category Id**.

Your request must also include a number of required headers:

- . Header for your client key. For example: .
- . The content type of the payload. The required format is: .

The request body should contain an array that includes a JSON object with a property that specifies the text that you want to translate:

There are different ways you can send your request to the API, including using the C#, Python, and curl. For instance, to make a quick call, you can send a POST request using curl:

The request above makes a call to translate a sentence from English to Dutch.

### 
# Response returned

The response returns a response code of if the request was successful. It also returns a response body that contains the translated text, like this:

If the request wasn't successful, then a number of different status codes may be returned depending on the error type, such as (missing or invalid query parameters). See [Response status codes](/en-us/azure/ai-services/translator/reference/v3-0-translate?tabs=curl) for a full list of codes and their explanation.

Note

For more information about custom translation, see [Quickstart: Build, publish, and translate with custom models](/en-us/azure/ai-services/translator/custom-translator/quickstart).



