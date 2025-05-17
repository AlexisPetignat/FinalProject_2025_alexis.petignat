# FinalProject_2025_alexis.petignat
Recommender System final project. Thou shall disover the mighty system one has built.

# Introduction

Behold! This is the Final Project for the Recommender System – the grand culmination of humanity’s technological dabblings (at least until tea time). With great pomp, ceremony, and possibly a duck, we present a marvel of modern computing: a system designed to divine which N videos a user might fancy – all based on the sacred scrolls of the KuaiRec dataset.

Now, before you lob tomatoes or shout "Ni!", a humble request: do bear in mind that we are but simple folk, valiantly juggling multiple quests (some involving dragons, deadlines, and dubious dietary choices). The time bestowed upon this endeavour was shorter than a hedgehog’s temper – so be gentle, or we shall be forced to release... the feedback evil spells.

Okay that's enough Monty Python fort today.



# The dataset

I think you do not need a link to download the dataset. The data must be placed in the same directory as the recommender.ipynb notebook.
The KuaiRec dataset is a large-scale benchmark dataset for short video recommendation, collected from the Kuaishou platform, a major Chinese short-video app. It includes rich multimodal content like user interaction logs, video metadata, and user profiles.


# Data engineering

Several features were built for the recommending: 
- Binary vectors representing the features for each videos.
- A like/view ratio for each video, which is a great indicator of how good a video is.
- A user-item matrix. Feel free to build it for the complete dataset if you can, it makes my notebook crash if I do.


# Models

Several models have been developped:
- An ALS model
- A content-based filtering model
- An attempt at two-towers (which failed because im on arch and I cant figure out how to install nvidia stuff for the training with tensorflow).


# Recommender System 

We based our quality analysis on several metrics, such as:
- Precision@k which symbolizes how relevant your recommendations are, which is by definition useful in the use case.
- Recall@k which symbolizes how many of the relevant items were suggested. This is good to ensure coverage in the recommendation
- NDCG, which gives an idea about the ranking of you recommendations.

We also combined all the models we created to make one bigger model, taking into account the ALS, the friends, the content of the video. I wanted to also take the video tags directly into account but I lacked time (see 4.2). Our final model works well but lacks Recall. I suspect there is an issue in my code putting the Recall lower than it should be. Who knows?

# Conclusion

And so, brave data knight, thou hast ventured deep into the perilous realm of recommendations — armed with nothing but a few DataFrames, a spark of Keras magic, and the ever-faithful pandas.

You hath trained ALS like a wild stallion, summoned cosine similarity with incantations of MultiLabelBinarizer, and forged Two Towers that did crumble under the weight of cold-start doom. You hath calculated Precision@k, Recall@k, NDCG@k as though thine life depended on it (which, for us students, it may well do).

Though thou may not have found the Holy Grail (i.e., 100% recall), thy system now recommends about mightily, much like an oracle with a strong preference for cat videos and dance trends.

Rejoice! For your model doth return relevant videos, and the peasants are marginally more entertained.

    “And the Lord did grin… and the people did feast upon the recommended content, and the engineers did debug no more (for five minutes).”

Go forth, noble recommender!
