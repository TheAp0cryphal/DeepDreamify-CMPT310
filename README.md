# Result

![image](https://user-images.githubusercontent.com/70075553/180347772-a4b9929d-e734-4ac1-87f2-5585be6a1f69.png)
![image](https://user-images.githubusercontent.com/70075553/180347777-f2ca1f65-0d11-451f-ac7b-c95322cd11dd.png)

Discuss the results (using charts and graphs where possible). Compare the performance of the various models. Was the performance what you expected?

Which system performed best? Why? Which system had the worst performance? Why?

Provide some ideas to try that could improve the performance of the models (i.e., Future Work).

# DISCUSSION

Comparing the performance of the various models.

SVM Normal [0.5771144278606966] vs SVM Dream [0.46766169154228854]

Decision Tree Normal [0.4925373134328358] vs Decision Tree Dream [0.5323383084577115]

Random Forest Normal [0.5870646766169154] vs Random Forest Dream [0.46766169154228854]

Ensemble Soft Voting - SVM, Decision Tree, Random Forest - Normal [0.48756218905472637] , Dream [0.5323383084577115]

Ensemble Hard Voting - SVM, Decision Tree, Random Forest - Normal [0.572139303482587], Dream [0.46766169154228854]

Using Dreamify on the datasets might have changed the images a lot in visual sense, however, in pixels it changesonly by a few values here and there and there are no significant changes.

SVM normal seems to work at par with the Random Forest having best accuracy out of all.

Decision Tree Dream unexpectedly performs better on DeepDream than the normal one.

Ensemble Hard voting decides the voting class on basis on output classes of the 3 models. An ensemble model is theoretically better in some cases and it works on consensus of the outputs of all 3 models it was fed.

Ensemble Soft does not exactly outputs the class value of to the data, it gives a predicted probability function for the classifier. It is recommended to use only when the models are well calibrated. Hard seems to have performed better in overall sense, because because of SVM and Random Forest performing better on the normal dataset as individual models, having low scores in the transformed section would be due SVM and Random Forest performing badly on the Deep Dream. It basically took the average of all 3 models and computed an ensemble prediction. We can see the values are equally bad for svm and randomforest on deepdream and that is what Ensemble Hard shows us.

I actually expected SVM would perform better than random forest due to its proficiency in binary class systems while forests work better for multiclass problems. Random Forest would've worked even better if their were some catergorical features.

Decision Trees can easily overfit and that's probably one of the reason's its normal score is so low. I am not entirely sure why decision tree performed better on dream data. I did not expect it would perform best on dream data when its normal score is not par with the other models that are better suited to this problem.

We can use accuracy_score since there isn't a majority class here. A confusion matrix was also an option but since it wasn't expected, I just used the accuracy_score metric.

I also managed to run a single layer KNN on a sequential model. image.png The accuracy that provided me was way better.
Tutorial https://www.youtube.com/watch?v=YrMy-BAqk8k&t=767s

I think one of the deciding factors to performance improvement was the limitation of 1000 images and the lack of better models. Our computers arent powerful enough to compress and train large amount of data. Especially in visual ML training model a lot would depend on the amount of data and the configuration of the models. The more sensitive the models are, the better they would likely perform. It would be better to go through the data to get only the kind of images that really really improve the learning curve of the model. I also think the models we used were not especially equipped to deal with a problem like image classification

