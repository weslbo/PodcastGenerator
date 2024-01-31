# PodcastGenerator

This repository with a [python notebook](Generator.ipynb) support the creation of a podcast .mp3 audio file.

When you listen to the generated podcast, you will notice an engaging conversation between the host and a guest, as they talk about the content of your choice. You determine what they talk about, as you can provide a list of web pages to take content from.

The podcast generator uses the following technique to create the .mp3:

1. Define a list of url's you want to use as the input for the podcast content. The generator will automatically fetch the content of these web pages and translate to markdown language
2. Define who are the host and the guest
3. For each web page, generate a podcast transcript (where the host and the guest have a conversation). This uses Azure OpenAI gpt3.5 deployed model.
4. Transform the podcast transcript to SSML (Speech Synthesis Markup Language)
5. Transform the SSML output to audio using Azure Cognitive Service Speech API
6. Combine all the .mp3 files into one output