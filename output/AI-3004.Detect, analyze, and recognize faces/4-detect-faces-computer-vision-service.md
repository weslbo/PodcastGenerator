
# 
# Detect faces with the Azure AI Vision service

To detect and analyze faces with the Azure AI Vision service, call the **Analyze Image** function (SDK or equivalent REST method), specifying **People** as one of the visual features to be returned.

In images that contain one or more people, the response includes details of their location in the image and the attributes of the detected person, like this:

For more information on Azure AI Vision people detection, see the [People detection concept page](/en-us/azure/ai-services/computer-vision/concept-people-detection?azure-portal=true)

Note

Azure AI Vision previously included age and gender prediction, however that has been removed as a safeguard for responsible use. You can read more about our [Responsible AI Investments here](https://azure.microsoft.com/blog/responsible-ai-investments-and-safeguards-for-facial-recognition/).



