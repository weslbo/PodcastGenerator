
# 
# Use a knowledge base

To consume the published knowledge base, you can use the REST interface.

The minimal request body for the function contains a question, like this:

| Property | Description |
| --- | --- |
| question | Question to send to the knowledge base. |
| top | Maximum number of answers to be returned. |
| scoreThreshold | Score threshold for answers returned. |
| strictFilters | Limit to only answers that contain the specified metadata. |

The response includes the closest question match that was found in the knowledge base, along with the associated answer, the confidence score, and other metadata about the question and answer pair:

[Continue](/en-us/)

