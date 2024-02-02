
# 
# Analyze an image

To analyze an image, you can use the **Analyze Image** REST method or the equivalent method in the SDK for your preferred programming language, specifying the visual features you want to include in the analysis (and if you select categories, whether or not to include details of celebrities or landmarks). This method returns a JSON document containing the requested information.

Note

Detection of celebrities will require getting approved through a [Limited Access policy](https://aka.ms/cog-services-limited-access). You can read more about the [addition of this policy](https://azure.microsoft.com/blog/responsible-ai-investments-and-safeguards-for-facial-recognition/) to our Responsible AI standard. Celebrity recognition is seen in some screenshots, however is not included in the lab.

**C#**

**Python**

You can also use scoped functions to retrieve specific subsets of the image features, including the image description, tags, and objects in the image.

The JSON response for image analysis looks similar to this example:



