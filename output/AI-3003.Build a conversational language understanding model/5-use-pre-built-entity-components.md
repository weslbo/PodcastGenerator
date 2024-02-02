
# 
# Use pre-built entity components

You can create your own language models by defining all the intents and utterances it requires, but often you can use prebuilt components to detect common entities such as numbers, emails, URLs, or choices.

For a full list of prebuilt entities the Azure AI Language service can detect, see the list of [supported prebuilt entity components.](/en-us/azure/ai-services/language-service/conversational-language-understanding/prebuilt-component-reference?azure-portal=true)

Using prebuilt components allows you to let the Azure AI Language service automatically detect the specified type of entity, and not have to train your model with examples of that entity.

To add a prebuilt component, you can create an entity in your project, then select **Add new prebuilt** to that entity to detect certain entities.

[![Screenshot of adding a prebuilt entity component.](../../wwl-data-ai/build-language-understanding-model/media/add-prebuilt-entity-small.png)](../../wwl-data-ai/build-language-understanding-model/media/add-prebuilt-entity.png#lightbox)

You can have up to five prebuilt components per entity. Using prebuilt model elements can significantly reduce the time it takes to develop a conversational language understanding solution.



