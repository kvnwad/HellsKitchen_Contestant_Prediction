# Hell's Kitchen Contestant Prediction

After fitting a logistic regression model to find contestants who were in the top 3, and using `signature_dish_score_numeric`, `times_nominated`, and `times_as_bo_w_announcer` as predictors an accuracy of **0.9375000** was achieved.

A precission of **0.875** was achived and a recall of **0.7777778**

The confusion matrix is:           

|  | Truth ||
| -------- | ------- |-------|
| **Prediction** | 0 | 1 |
| 0 | 38 | 2 |
| 1 | 1 | 7 |


## Discussion on feature selection

The features were chosen with care. `challenges_won` and `services_won`, from a viewer's perspective, might provide too much help to the model. A higher number of wins usually indicates a greater likelihood of a contestant making it to the top 3. In contrast, a low number of wins may suggest that the contestant was eliminated early on.

- `blind_taste_test_score_numeric` is a good indicator of a contestant's palate. This challenge is conducted only once and reflects the contestant’s individual ability. However, since this feature contains a large number of missing values, it will not be used.

- `times_nominated` represents how many times the contestant was put up for elimination by their team. While one could argue that more nominations might correlate with a longer presence in the competition, the show typically does not eliminate the fourth-place contestant based on nominations. Instead, the host selects who is eliminated, making this feature less informative.

- `times_as_bo_w_announcer` stands for "Best of the Worst" announcer. The announcer is chosen by the host to nominate fellow contestants for elimination. It appears the host usually selects someone who made the fewest mistakes or demonstrated strong leadership qualities. For this reason,`times_as_bo_w_announcer` will be used as a feature.

- `signature_dish_score_numeric` is arguably the most important feature. This challenge is the first one completed by the contestants and highlights their individual cooking ability. Performing well in this challenge helps contestants get on the host’s radar. Therefore, this feature will also be included.


