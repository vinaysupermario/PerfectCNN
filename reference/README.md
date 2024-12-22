# CODE 1: The Setup

_"Every **setback** is a failure in getting the **setup** right"_
    --Successful Student

Target:

1. Get the set-up right
2. Set Transforms
3. Set Data Loader
4. Set Basic Working Code
5. Set Basic Training  & Test Loop
6. Results:
    1. Parameters: 6.3M
    2. Best Training Accuracy: 99.99
    3. Best Test Accuracy: 99.24
7. Analysis:
    1. Extremely Heavy Model for such a problem
    2. Model is over-fitting, but we are changing our model in the next step

# CODE 2: The Skeleton

_"Great Models are built with even greater **skeletons**"_ 
    --Successful Student

Target:

1. Get the basic skeleton right. We will try and avoid changing this skeleton as much as possible. 
2. No fancy stuff
3. Results:
    1. Parameters: 194k
    2. Best Train Accuracy: 99.35
    3. Best Test Accuracy: 99.02
4. Analysis:
    1. The model is still large, but working. 
    2. We see some over-fitting

# CODE 3: The Lighter Model

_"They say crying makes the **Heart/Model** lighter"_   --Successful Student

Target:

1. Make the model lighter
2. Results:
    1. Parameters: 10.7k
    2. Best Train Accuracy: 99.00
    3. Best Test Accuracy: 98.98
3. Analysis:
    1. Good model!
    2. No over-fitting, model is capable if pushed further

# CODE 4: The Batch Normalization

_"The great enemy of any totalitarian dataset is **Batch Normalization**"_  --Successful Student

Target:

1. Add Batch-norm to increase model efficiency.
2. Results:
    1. Parameters: 10.9k
    2. Best Train Accuracy: 99.9
    3. Best Test Accuracy: 99.3
3. Analysis:
    1. We have started to see over-fitting now.
    2. Even if the model is pushed further, it won't be able to get to 99.4