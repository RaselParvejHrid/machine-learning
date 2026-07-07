# Project 003

Started on July 06, 2026

Completed on July 07, 2026

## Problem Statement

Extend your [Iris project](../project002) again.

This time:

1. Keep your preprocessing inside a Pipeline.
2. Use GridSearchCV with 5-fold cross-validation.
3. Tune n_neighbors over a reasonable range (for example, odd values from 1 to 15).
4. Report:
   * the best value of k,
   * the mean cross-validation score,
   * the final test accuracy.
5. In your README, explain why the test set was not used during hyperparameter selection.

# Why was the test set not used during hyperparameter selection?

We select hyperparameter before training the model, to train the model.


And test set is to simulate future unseen data for models. So, a model is to see test data only when it's ready and it's trained, not during training.


As hyperparameter selection is a part of training or a part of pre-training, it's not allowed to see the test set.
