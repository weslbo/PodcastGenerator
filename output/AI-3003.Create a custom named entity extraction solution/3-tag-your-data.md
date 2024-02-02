
# 
# Label your data

Labeling, or tagging, your data correctly is an important part of the process to create a custom entity extraction model. Labels identify examples of specific entities in text used to train the model. Three things to focus on are:

- **Consistency** - Label your data the same way across all files for training. Consistency allows your model to learn without any conflicting inputs.
- **Precision** - Label your entities consistently, without unnecessary extra words. Precision ensures only the correct data is included in your extracted entity.
- **Completeness** - Label your data completely, and don't miss any entities. Completeness helps your model always recognize the entities present.

[![Screenshot of labeling an entity in Language Studio.](../../wwl-data-ai/custom-name-entity-extraction/media/tag-entity-screenshot.png)](../../wwl-data-ai/custom-name-entity-extraction/media/tag-entity-screenshot.png#lightbox)

## 
# How to label your data

Language Studio is the most straight forward method for labeling your data. Language Studio allows you to see the file, select the beginning and end of your entity, and specify which entity it is.

Each label that you identify gets saved into a file that lives in your storage account with your dataset, in an auto-generated JSON file. This file then gets used by the model to learn how to extract custom entities. It's possible to provide this file when creating your project (if you're importing the same labels from a different project, for example) however it must be in the [Accepted custom NER data formats](/en-us/azure/ai-services/language-service/custom-named-entity-recognition/concepts/data-formats).
For example:

| Field | Description |
| --- | --- |
|  | Array of labeled documents |
|  | Path to file within container connected to the project |
|  | Language of the file |
|  | Array of present entities in the current document |
|  | Inclusive character position for start of text |
|  | Length in characters of the data used in training |
|  | Name of entity to extract |
|  | Array of labeled entities in the files |
|  | Inclusive character position for start of entity |
|  | Length in characters of the entity |
|  | Which dataset the file is assigned to |



