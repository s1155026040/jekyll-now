cient Traffic-Sign Recognition with Scale-aware CNN

Multi-loss way

The model is not trained from end to end?

Paper Summary. Please summarize the paper in your own words. ( Required, Visible To Authors During Feedback and After Decision Notification )

The paper aims to recognize traffic signs on images using deep neural network. The authors proposed two CNN architecture, with one for region proposal and one for classification of proposed region. The authors claim to have achieved better than state-of-the-art results on Swedish Traffic Signs Dataset (STSD).

   Paper Strengths. Describe positive aspects of the paper. 
What is of interest to the community? Consider criteria such as novelty, clarity, technical achievements (theoretical or practical), and thoroughness of validation.

If accepted, what aspects would be cite-worthy? ( Required, Visible To Authors During Feedback and After Decision Notification )

The model contains mainly two parts: detection network and classification network. The detection network is a pyramid structure and predicts at per-pixel level. Each pixel is given a probability of weather it is a traffic sign pixel or not. It’s similar to traffic sign object segmentation. In terms of technical achievements, the model achieves the best result on STSD dataset.

   Paper Weaknesses. 
Discuss negative aspects such as lack of novelty or clarity, technical errors, missing validation or proofs, etc.. Please justify your comments with details.

If you think the paper is not novel, explain why and provide specific references. Be kind. ( Required, Visible To Authors During Feedback and After Decision Notification )

In the evaluation, only precision and recall is evaluated (in line 303). It would be good for the authors to also compare F1 score.

In the detection network, the label for each bounding box itself contains noise. Would it be better to just use the ground truth bounding box as labels instead of proposing a certain amount to bounding boxes with IoU > 0.7 as positive bounding box and bounding boxes with IoU < 0.3 as negative labels? Can authors provide comparison over these two methods?

For the classification network, the authors only feed features extracted within detected bounding box to the fusion-net if I understand correctly. It would be good to also consider combining global features extracted from the whole image and local features extracted from proposed region. In that way, if the bounding box is predicted too far away, the fusion-net still get an overview of the image.

   Overall Rating. Try to avoid choosing "Borderline."
  ( Required, Visible To Authors During Feedback and After Decision Notification )
Strongly accept.

   Overall Evaluation. 
Please convey to the authors, the Area Chair, and to fellow reviewers, how you decided your Overall Rating. Good ideas need a reviewer to champion their paper, and bad papers need constructive criticism. What key things would you like the authors to include in their rebuttal? ( Required, Visible To Authors During Feedback and After Decision Notification )

I’ve read through the whole paper in detail, with specific focus on the model and experiment sessions. Overall, the paper contains sufficient amount of novelty and technical achievements.

   Confidence. How certain are you of your rating? Choose "Very Confident" if you are an expert working in the area, "Confident" if you are not an expert but are knowledgeable, and "Not Confident" in all other cases.
  ( Required, Visible To Authors During Feedback and After Decision Notification )
Confidence

   Confidential Comments to Chairs
  ( Optional )
   Reviewed by. Leave blank by default. Answer will only be seen by Chairs.
  ( Optional )
===========================================================

take away: “Fusing features from different layers in a CNN is proved to be effective in improving accuracy in many tasks”
“The Inception module performs multi size convolution at the same time. All the results are then concatenated. And then global average pooling.” “Non-maximum suppression over all the regions proposals according to their classification scores”
