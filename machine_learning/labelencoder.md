# Label Encoder
## What is it?
According to scikit-learn, a label encoder "encodes labels with value between 0 and n_classes-1" ([scikit-learn docs](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html)).

It is necessary for training a model, because algorithms require input and output variables to be numeric. So we need to binarize our categorical data.

Steps for label encoding

1. import LabelEncoder class from sklearn library
2. fit and transform data
3. replace existing data with new encoded data.

## Label Encoder vs One Hot Encoder
Depending on the data, there could possibly be a problem with label encoding. The model There might be situations in which the model interprets the data to be in some order (0 < 1 < 2), even though each row is an individual category. This problem can be avoided by One Hot Encoding.

One hot encoding takes another step beyond label encoding, and replaces the number labels with 1s and 0s. Example:

| Label 1 | Label 2 | Label 3 |
|:-------:|:-------:|:-------:|
| 1 | 0 | 0 |
| 0 | 1 | 0 |
| 0 | 0 | 1 |
