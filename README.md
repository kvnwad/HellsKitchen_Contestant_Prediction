# Hells Kitchen Contestant Prediction

After fittig a logistic regression model to find contestants who were in the top 3, and using `signature_dish_score_numeric`, `times_nominated`, and `times_as_bo_w_announcer`  as predictors an accuracy of *0.9375000* was achieved.

A precission of *0.875* was achived and a recall of *0.7777778*

The confusion matrix is:           
            Truth
Prediction  0  1
         0 38  2
         1  1  7


## Discussion on feature selection

The features were chosen as such, `challenges_won` and `services_won` from the perspective of a viewer of the show might offer too much help to the model as a higher number of wins usually indicates that the contestant has higher a chance of being in top 3 compared someone who has low wins potentially meaning the contestant was eliminated.

- `blind_taste_test_score_numeric` is good indicator of the contestants palate, this challenge is only done once, and represents the contestants ability individually, though this parameter has a lot NA values, therefore will not be used.

- `times_nominated` is how many times the contestant was put up for elimination by their team, while one can argue that a higher number of nominations results in a potential higher standing, the show does not typically have it so that the last 4th contestant is eliminated by nomination and instead is chosen to be eliminated by the host.

- `times_as_bo_w_announcer` stands for best of the worst, or announcer. The announcer is chosen by the host to announce the fellow contestants who are being nominated for elimination. It appears the host usually picks the contestants that had the least mistakes or has the strongest values among the group to announce. For this reason `times_as_bo_w_announcer` will also be used as a feature.

- `signature_dish_score_numeric` the most important feature, is the first challenge done by the contestants, this challenge highlights the contestants individual ability to cook a well rounded dish and earn a spot on the hosts radar. This will also be used as feature.


