# id2223_kth_lab2

In this lab, we fine-tuned a pre-trained transformer model, Whisper, to transcribe audio from Chinese to text. We provided a user interface to allow users to use the model. Also, we refactored the notebook into feature, training, and inference pipelines.

As for the implementation detail, In this lab, we stored the data on Google Drive and then mounted it into a shared Colab for training. The Chinese dataset is big, so we expanded data storage in Google Drive.
 
We improve the model performance using model-centric approach.
- tune hyperparameters:
  - fp16 greatly improves the speed of traning (available only on GPU).
