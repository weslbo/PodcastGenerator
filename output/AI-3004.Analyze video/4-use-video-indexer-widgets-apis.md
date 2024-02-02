
# 
# Use Video Analyzer widgets and APIs

While you can perform all video analysis tasks in the Azure Video Indexer portal, you may want to incorporate the service into custom applications. There are two ways you can accomplish this.

## 
# Azure Video Indexer widgets

The widgets used in the Azure Video Indexer portal to play, analyze, and edit videos can be embedded in your own custom HTML interfaces. You can use this technique to share insights from specific videos with others without giving them full access to your account in the Azure Video Indexer portal.

![Video Analyzer widgets in a custom web page](../../wwl-data-ai/analyze-video/media/widgets.png)

## 
# Azure Video Indexer API

Azure Video Indexer provides a REST API that you can use to obtain information about your account, including an access token.

You can then use your token to consume the REST API and automate video indexing tasks, creating projects, retrieving insights, and creating or deleting custom models.

For example, a GET call to REST endpoint returns the specified logo. In another example, you can send a GET request to , which returns details of videos in your account, similar to the following JSON example:

## 
# Deploy with ARM template

Azure Resource Manager (ARM) templates are available to create the Azure AI Video Indexer resource in your subscription, based on the parameters specified in the template file.

For a full list of available APIs, see the [Video Indexer Developer Portal](https://api-portal.videoindexer.ai/).



