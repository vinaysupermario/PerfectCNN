# Step 1 : Set-Up

_"Every **setback** is a failure in getting the **setup** right"_
    --Successful Student

## Target:

1. Get the set-up right
2. Set Transforms
3. Set Data Loader
4. Set Basic Working Code
5. Set Basic Training  & Test Loop
6. Results:
    1. Parameters: 6.3M
    2. Best Training Accuracy: 99.99
    3. Best Test Accuracy: 99.40
7. Analysis:
    1. Extremely Heavy Model for such a problem
    2. Model is over-fitting, but we are changing our model in the next step

    Target:

# Step 2 : Editting the Skeleton

_"Great Models are built with even greater **skeletons**"_ --Successful Student

## Target:

1. Get the basic skeleton right. We will try and avoid changing this skeleton as much as possible.
2. No fancy stuff
3. Results:
    1. Parameters: 194k
    2. Best Train Accuracy: 99.51
    3. Best Test Accuracy: 98.96
4. Analysis:
    1. The model is still large, but working.
    2. We see some over-fitting

# Step 3 : Making the Model Lighter

_"They say crying makes the **Heart/Model** lighter"_ --Successful Student

## Target:

1. Make the model lighter
2. Results:
    1. Parameters: 10.7k
    2. Best Train Accuracy: 99.00
    3. Best Test Accuracy: 98.98
3. Analysis:
    1. Good model!
    2. No over-fitting, model is capable if pushed further

# Step 4 : Adding Batch Normalization

_"The great enemy of any totalitarian dataset is **Batch Normalization**"_  --Successful Student

## Target:

1. Add Batch-norm to increase model efficiency.
2. Results:
    1. Parameters: 17.3k
    2. Best Train Accuracy: 99.99
    3. Best Test Accuracy: 99.43
3. Analysis:
    1. We have started to see over-fitting now.
    2. Even if the model is pushed further, it won't be able to get to 99.4

# Step 5 : Adding Regularization

_"Be somebody who gives the right kind of **Regularization** to All Models"_ --Successful Student

## Target:

1. Add Regularization - Dropout
2. Results:
    1. Parameters: 17.3k
    2. Best Train Accuracy: 99.56
    3. Best Test Accuracy: 99.37
3. Analysis:
    1. Regularization working.
    2. But with the current capacity, not possible to push it further.
    3. We are also not using GAP, but depending on a BIG-sized kernel


# Step 6 : Replace Output Layer by Global Average Pooling

_"The Capacity to learn is a **Gift**, the Ability to learn is a **Skill**, the Willingness to learn is a **Choice**"_    --Successful Student

## Target:

1. Add GAP and remove the last BIG kernel.
2. Results:
    1. Parameters: 12.4
    2. Best Train Accuracy: 98.88
    3. Best Test Accuracy: 99.14
3. Analysis:
    1. Adding Global Average Pooling reduces accuracy - WRONG, it doesn't because it also reduces the parameters.
    2. WSince we have reduced model capacity, a reduction in performance is expected. We need to increase the Capacity of Model.

# Step 7 : Fix the Model Capacity

_"The Capacity to learn is a **Gift**, the Ability to learn is a **Skill**, the Willingness to learn is a **Choice**"_    --Successful Student

## Target:

1. Fix the model capacities in the middle layer.
2. Don't bake the cake unless you have so many features to capture. Increase, Decrease, Increase cycle.
3. Result:
    1. Parameters: 7.5k
    2. Best Train Accuracy: 99.14
    3. Best Test Accuracy: 99.35
4. Analysis:
    1. Quite Possibly we need to add more capacity, especially at the end.
    2. Closer analysis of MNIST can also reveal that just at RF of 5x5 we start to see patterns forming.
    3. We can also increase the capacity of the model by **adding a layer after GAP!**

# Step 8 : Add Final Layer after GAP

_"Don't rush anything, when the time is right, it'll happen/**Add Maxpooling**"_  --Successful Student

## Target:

1. Increase model capacity at the end (add layer after GAP)
2. Results:
    1. Parameters: 9.8k
    2. Best Train Accuracy: 99.41
    3. Best Test Accuracy: 99.40 (11th Epoch)
3. Analysis:
    1. Works!
    2. But we're not seeing 99.4 or more as often as we'd like. We can further improve it.
    3. The model is not over-fitting at all. Least △ (test-train) accuracy observed.
    4. Seeing image samples, we can see that we can add slight rotation.

# Step 9 : Add Image Augmentation in Training

_"Once your Model is ready, only then apply **Augmentation**"_ --Successful Student

## Target:

1. Add rotation, we guess that 5-7 degrees should be sufficient.
2. Results:
    1. Parameters: 9.8k
    2. Best Train Accuracy: 99.16
    3. Best Test Accuracy: 99.42 (19th Epoch)
3. Analysis:
    1. The model is under-fitting now. This is fine, as we know we have made our training data harder.
    2. The test accuracy is also up, which means our test data had few images that had transformation difference w.r.t. train dataset
    3. We can counter the under-fitting by increasing more layers in the middle.

# Step 10 : Adding more layer in middle & Playing with the Learning Rate

_"Stop playing god, that's morgan's job, don't mess naively with **Learning Rates**"_   --Successful Student

Target:

1. The model was under-fitting, so needed to add one more Convolution layer.
2. Experiment with changing the Learning Rate.
3. Result:
    1. Parameters: 12.1k
    2. Best Train Accuracy: 99.23
    3. Best Test Accuracy: 99.50
3. Analysis:
    1. The model is still a bit under-fitting.
    2. We're finally getting test accuracy greater than 99.40% on test results. Consistently Enough.
    3. Finding a good LR schedule is hard.