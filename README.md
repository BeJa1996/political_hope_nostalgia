# Hope and Nostalgia Expressions in UK Political Communication
This project investigates the use of hope and nostalgia expressions by UK politicians and political parties. It consists of three parts.

## I Gathering YouTube channels, videos and transcripts from UK MPs and largest Parties
I performed a comprehensive search of YouTube Channels which feature UK MPs with Google's YouTube API. 
- You can find those channels in [UK_MP_Youtube_channels.csv] (https://github.com/BeJa1996/political_hope_nostalgia/blob/main/UK_MP_Youtube_channels.csv) together with an automated assessment. The API also returned channels that were not directly related. Therefore, you can also find an automatic assessment of whether the MP's name is actually in the title and a manual assessment of whether the channels feature the MP. Thereby, I only chose one channel per MP. I also added statistics to each channel.
- For some of these channels and the official channels of the Labour and Conservative Party, I searched for videos and downloaded statistics and transcripts. You can find those in [UK_MP_Youtube_videos.csv](https://github.com/BeJa1996/political_hope_nostalgia/blob/main/UK_MP_Youtube_videos.csv).
- The whole process is documented in [UK_MP_Youtube_ChannelsVideosTranscripts.ipynb](https://github.com/BeJa1996/political_hope_nostalgia/blob/main/UK_MP_Youtube_ChannelsVideosTranscripts.ipynb)

## II Fine-Tuning Classifiers to Categorize Hope and Nostalgia Expressions
I trained a Naive Bayes Classifier and three different Transformer models to detect hope and nostalgia on respective datasets. My Transformer Models for hope reached an F1 macro > 0.8 on a held-out part of the dataset, and those on nostalgia an F1 macro > 0.9.
- The training process is documented in [Hope_Nostalgia_Classifier_Training](https://github.com/BeJa1996/political_hope_nostalgia/blob/main/Hope_Nostalgia_Classifier_Training.ipynb).
-  The fine-tuned hope Naive Bayes is [hope_nb_model.joblib](https://github.com/BeJa1996/political_hope_nostalgia/blob/main/hope_nb_model.joblib);
-  the fine-tuned nostalgia Naive Bayes is [nostalgia_nb_model.joblib](https://github.com/BeJa1996/political_hope_nostalgia/blob/main/nostalgia_nb_model.joblib);
-  and the transformer models are at my [Huggingfac Profile](https://huggingface.co/beja1996).

## III Applying the Fine-Tuned Classifiers to the Video Transcripts
In the last step, I applied those classifiers to identify how many expressions of hope and nostalgia can be found in the videos of progressive and conservative politicians. 
- The analysis process is in [UK_MPs_HopeNostalgia_Analysis.ipynb](https://github.com/BeJa1996/political_hope_nostalgia/blob/main/UK_MPs_HopeNostalgia_Analysis.ipynb).
- The results of the classifiers can be found in [transcripts_analysed.csv](https://github.com/BeJa1996/political_hope_nostalgia/blob/main/transcripts_analysed.csv)
