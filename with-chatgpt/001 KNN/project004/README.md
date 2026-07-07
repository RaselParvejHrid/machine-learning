# Project 004

Started on July 07, 2026

Completed on July 07, 2026

## Problem Statement

Extend your [Iris project](../project003) one more time.

This time, compare:

* weights="uniform"
* weights="distance"

using GridSearchCV.

Your parameter grid might include both:

* different values of n_neighbors
* different weights options

Then answer in your README:

* Which combination performed best?
* Was the improvement substantial?
* Why do you think distance weighting helped (or didn't help) on the Iris dataset?

# Which combination performed best?
`n_neighbors = 9`
`weights = 'distance'`

# Was the improvement substantial?
No, not in this case. In [Project 003](../project003), with `n_neighbors = 3` and a default `wights = 'uniform'`, the accuracy was already 100%.

# Why do you think distance weighting helped (or didn't help) on the Iris dataset?
As in [Project 003](../project003), with `n_neighbors = 3` and a default `weights = 'uniform'`, the accuracy was already 100%, no, distance weighting isn't helping here, rather increasing computational complexity by increasing `n_neighbors` from 3 to 9.


