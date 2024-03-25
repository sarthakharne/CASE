# CASE

The models are not made public due to the double-blind reviewing process. For the final version, the repository will have the links to these models on huggingface.

In 'BERTPreTraining.py' the data path of a directory which contains the documents in .parquet format is expected. This code can be changed to suit ones requirements.

In all other documents the data path of a single csv file with the respective data is expected.
<li> In BERTFineTuning.py the source column is 'post' as set in the custom dataset. The target column contains binary values (0 or 1) and the name of this column is the disorder it indicates.
<li> In GemmaTraining.py the pre_training variable needs to be set to False for fine tuning. In the case of pre training the source column in the dataset is 'TEXT' while in the case of fine tuning this values is 'Post'. In the case of fine tuning, the target column is 'Generated Diagnosis Summary'
<li> In GemmaValidation.py the data path is set to the file generated by GemmaTraining.py after finetuning is done. The data file should have 'Predicted Diagnosis' column which is generated by the model and 'Generated Diagnosis Summary' column which is the reference summary obtained using the annotations from GPT-3.5
