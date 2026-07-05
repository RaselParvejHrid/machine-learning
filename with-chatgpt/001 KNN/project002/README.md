# Project 002

Started on July 05, 2026

Completed on July 05, 2026

## Problem Statement

Extend your [Iris KNN project](../project001).

In addition to reporting accuracy:

* Compute the confusion matrix.
* Generate the classification report.
* Interpret the results in your README.

Don't just paste the output.

Answer questions like:

* Which class is easiest to classify?
* Which classes are confused with one another?
* Why might that happen?

# Interpretation

Interestingly, my model here gives accuracy, precision and recall all 100%, for `n_neighbors=5`. I have tried changing `random_state` in `train_test_split`, with no change in the metrics.

With `n_neighbors` set to `50`, the accuracy decreases to `93%`. The confusion matrix, then, is as below.

<table>
    <tr>
        <th rowspan="2" colspan="2"></th>
        <th colspan="3">Predicted Labels</th>
    </tr>
    <tr>
        <th>setosa</th>
        <th>versicolor</th>
        <th>virginica</th>
    </tr>
    <tr>
        <th rowspan="3">True Labels</th>
        <th>setosa</th>
        <td>10</td>
        <td>0</td>
        <td>0</td>
    </tr>
    <tr>
        <th>versicolor</th>
        <td>0</td>
        <td>8</td>
        <td>1</td>
    </tr> 
    <tr>
        <th>virginica</th>
        <td>0</td>
        <td>1</td>
        <td>10</td>
    </tr> 
</table>



And the Classification Report is as below.
<table>
    <tr>
        <th></th>
        <th>precision</th>
        <th>recall</th>
        <th>f1-score</th>
        <th>support</th>
    </tr>
    <tr>
        <th>setosa</th>
        <td>1.00</td>
        <td>1.00</td>
        <td>1.00</td>
        <td>10</td>
    </tr>
    <tr>
        <th>versicolor</th>
        <td>0.89</td>
        <td>0.89</td>
        <td>0.89</td>
        <td>9</td>
    </tr>
    <tr>
        <th>virginica</th>
        <td>0.91</td>
        <td>0.91</td>
        <td>0.91</td>
        <td>11</td>
    </tr>
</table>


## Which class is easiest to classify?

`setosa`. Confusion along neither row nor column.

## Which classes are confused with one another?

`versicolor` and `virginica`.

## Why might that happen?

I googled and see the two species. They look too similar visually. Maybe sepal and petal dimensions are close enough too. This closeness affects the model when `n_neighbors` is large enough, like `50`. But it was unable to affect the model with `n_neighbors` set to a small value like `5`.
