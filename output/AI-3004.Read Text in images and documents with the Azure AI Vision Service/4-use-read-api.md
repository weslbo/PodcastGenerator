
# 
# Use the Read API

To use the Read OCR feature, call the **ImageAnalysis** function (REST API or equivalent SDK method), passing the image URL or binary data, and optionally specifying a gender neutral caption or the language the text is written in (with a default value of **en** for English).

To make an OCR request to **ImageAnalysis**, specify the analysis features as .

**C#**

**Python**

If using the REST API, specify the feature as .

The results of the Read OCR function are returned synchronously, either as JSON or the language specific object of a similar structure. These results are provided as a complete result and broken down by *page*, then *words*, and then *lines*. Additionally, the text values are included at both the *line* and *word* levels, making it easier to read entire lines of text if you don't need to extract text at the individual *word* level.



