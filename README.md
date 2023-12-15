# id2223_kth_lab2

In this lab, we fine-tuned a pre-trained transformer model, Whisper, to transcribe audio from Chinese to text. We provided a user interface to allow users to use the model. Also, we refactored the notebook into `feature_engineering`, `training`, and `inference pipelines`.

As for the implementation detail, In this lab, we stored the data on Google Drive and then mounted it into a shared Colab for training. The Chinese dataset is large, so we expanded data storage in Google Drive.

 ## From the results we got from training, we think we can improve model performance using two ways:
 ### (a) Model-centric Approach
 - tune hyperparameters:
  - `fp16 = True` greatly improves the speed of training (available only on `GPU`).
  - `epoch number` Increase the number of epochs. It helps to fit the data better but it may cause overfitting. In the meantime, it takes more time to train, and the computation consumption is also considered.
  - `batch size` If you feed more data for each step to the model, it takes longer to update.
  - `learning rate` Higher learning rate may converge fast but with a high risk of missing local maxima. Smaller learning rates may take a long time to update the weights.
  - `model` We can choose other models like Whisper-large. It may show a better performance than Whisper-small. However, it will cost more time and space. 
### (b) Data-centric approach
 - Feed more data
 - Process the data with different methods like cutting each sample into several clips and then shuffling them and re-combining them together.

## Model Result Visualization
(a) Data size comparison (9588 & 5811):
![image](https://github.com/Antares28/id2223_kth_lab2/blob/main/img/Comparison%20between%20data%20sizes.png)
(b) Model choice comparison (Whisper-small & Wisper-tiny):
![image](https://github.com/Antares28/id2223_kth_lab2/blob/main/img/Comparison%20between%20models.png)
(c) Output comparison with video input (Whisper-small & Wisper-tiny):
![image](https://github.com/Antares28/id2223_kth_lab2/blob/main/img/Output%20comparison.png)
ture words:
![image](https://github.com/Antares28/id2223_kth_lab2/blob/main/img/example_video_words.png)


## Interface URL:
- `microphone transcription UI`: https://80d0514c6249d9a923.gradio.live/
- `video transcription UI`: https://d2a540b97f0b5bee66.gradio.live/


