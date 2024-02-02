
# 
# Improve question answering performance

After creating and testing a knowledge base, you can improve its performance with *active learning* and by defining *synonyms*.

## 
# Use active learning

Active learning can help you make continuous improvements to get better at answering user questions correctly over time. People often ask questions that are phrased differently, but ultimately have the same meaning. Active learning can help in situations like this because it enables you to consider alternate questions to each question and answer pair. Active learning is enabled by default.

To use active learning, you can do the following:

### 
# Create your question and answer pairs

You create pairs of questions and answers in Language Studio for your project. You can also import a file that contains question and answer pairs to upload in bulk.

[![A screenshot showing how to import a file with question and answer pairs.](../../wwl-data-ai/create-question-answer-solution-ai-language/media/import-file-small.png)](../../wwl-data-ai/create-question-answer-solution-ai-language/media/import-file.png#lightbox)

### 
# Review suggestions

Active learning then begins to offer alternate questions for each question in your question and answer pairs. You access this from the Review suggestions pane:

[![A screenshot of the Review suggestions pane.](../../wwl-data-ai/create-question-answer-solution-ai-language/media/review-suggestions-small.png)](../../wwl-data-ai/create-question-answer-solution-ai-language/media/review-suggestions.png#lightbox)

You review, and then accept or reject these alternate phrases suggested for each question by selecting the checkmark or delete symbol next to the alternate phrase. You can bulk accept or reject suggestions using the **Accept all suggestions** or **Reject all suggestions** option at the top.

You can also manually add alternate questions when you select **Add alternate question** for a pair in the Edit knowledge base pane:

[![A screenshot showing the Add alternate question option on the Edit knowledge base pane.](../../wwl-data-ai/create-question-answer-solution-ai-language/media/add-alternate-questions-manual-small.png)](../../wwl-data-ai/create-question-answer-solution-ai-language/media/add-alternate-questions-manual.png#lightbox)

Note

To learn more about active learning, see [Enrich your project with active learning](/en-us/azure/ai-services/language-service/question-answering/tutorials/active-learning).

## 
# Define synonyms

Synonyms are useful when questions submitted by users might include multiple different words to mean the same thing. For example, a travel agency customer might refer to a "reservation" or a "booking". By defining these as synonyms, the question answering service can find an appropriate answer regardless of which term an individual customer uses.

To define synonyms, you use the REST API to submit synonyms in the following JSON format:

Note

To learn more about synonyms, see the [Improve quality of response with synonyms](/en-us/azure/ai-services/language-service/question-answering/tutorials/adding-synonyms).

[Continue](/en-us/)

