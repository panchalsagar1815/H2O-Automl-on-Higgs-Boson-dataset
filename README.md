# H2O-Automl-on-Higgs-Boson-dataset

The evaluation metric is the approximate median significance (AMS):


where

s, b : unnormalized true positive and false positive rates, respectively,
b_r =10 is the constant regularization term,
\\(\log\\) is the natural log.
More precisely, let \\((y_1, \ldots, y_n) \in \{\text{b},\text{s}\}^n\\) be the vector of true test labels, let \\((\hat{y}_1, \ldots, \hat{y}_n) \in \{\text{b},\text{s}\}^n\\) be the vector of predicted (submitted) test labels, and let \\((w_1, \ldots, w_n) \in {\mathbb{R}^+}^n\\) be the vector of weights. Then


and


where the indicator function \\(\mathbb{1}\{A\}\\) is 1 if its argument \\(A\\) is true and 0 otherwise.

EventId is a unique identifier for each event. The list of EventIds must correspond to the exact list of EventIds in test.csv, but the ordering can be arbitrary.
RankOrder is a permutation of the integer list [1,550000] . The higher the rank, the more signal-like is the event. Most predictors output a real-valued score for each event in the test set, in which case RankOrder is just the ordering of the test points according to the score. The RankOrder is not used for computing the AMS, but it allows the organizers to compute other metrics (e.g., ROC) related to the classification task, which is not captured entirely by the classification alone.
Class is either "b" or "s", and it indicates if your prediction (yi above in the formal definition) for the event is background or signal. The AMS will be calculated based on the (hidden) weights of events that you mark "s"
