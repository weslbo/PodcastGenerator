
# 
# Understand language detection, translation, and transliteration

Let's explore the capabilities of **Azure AI Translator**. These capabilities include:

## 
# Language detection

You can use the **Detect** function of the REST API to detect the language in which text is written.

For example, you could submit the following text to the endpoint using curl.

Here's the text we want to translate:

Here's a call using curl to the endpoint to detect the language of our text:

The response to this request looks as follows, indicating that the text is written in Japanese:

## 
# Translation

To translate text from one language to another, use the **Translate** function; specifying a single **from** parameter to indicate the source language, and one or more **to** parameters to specify the languages into which you want the text translated.

For example, you could submit the same JSON we previously used to detect the language, specifying a **from** parameter of **ja** (Japanese) and two **to** parameters with the values **en** (English) and **fr** (French). To do this, you'd call:

This would produce the following result:

## 
# Transliteration

Our Japanese text is written using Hiragana script, so rather than translate it to a different language, you may want to transliterate it to a different script - for example to render the text in Latin script (as used by English language text).

To accomplish this, we can submit the Japanese text to the **Transliterate** function with a **fromScript** parameter of **Jpan** and a **toScript** parameter of **Latn**:

The response would give you the following result:



