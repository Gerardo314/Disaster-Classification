## Slide 15

* Before evaluating the performance of each, we must state the importance of both, identifying true positives and true negatives in this classification problem, as misclassifying a disaster can yield high real-life consequence. Therefore, it is equally important to consider the accuracy and macro F1 performance of these models, out of which, roBERTa beats the benchmarks by 5 percetnage points.
* For this evaluation, we treat a postive as a correct identificaiton, and a negative as a misclissaficaiton.
* roBERTa performs particularly well on classifying earthquakes and floods due to the particular nature of their unique vocabulary, which can be attributed to self-attention and rich word-embeddings.

## Slide 16

* roBERTa, like the baseline, struggles to identify other disasters and non-disasters due to presence of metaphors, sarcasm, vague sentiment, and mixed events in these tweets.

## Slide 17

* This is evident in the confusion matrices of the baseline models -- as the logistic regression classifier and the SVC confuse non-disasters with other disasters and vice versa with significantly high frequency, compared to other misclassifciations.
* We can also see these models occassionally also confuse the other categories.

## Slide 18

* roBERTa, however, is more accurate in classifying the main disaster categories, but still confuses non-disasters and other disasters with each other, albeit to a relatively lesser extent.
* This analysis shows a surprising conclusion: that this NLP classification problem can be tackled with SVC, with relatively high F1, even compared to a sophisticated LSTM like roBERTa. Furthermore, we note that the word feature vectors are near-linearly separable in feature space; however, for tougher datasets, this may not hold true.

## Slide 19

* We can attribute some of the superioir performacne of roberta to its context window in its bidirectional recurrent architecture, as for these unseen text, roBERTa was able to correctly infer the disaster by connceting the circumstances surrounding particular disasters, such as the ground shaking and the trees being on fire.

## Slide 20

* The superiois performance comes at a cost; our expriment shows that even though roberta converged in just 4 epochs of training (on top of a pre-trained model), SVCs are still far more lightweight and sustainable on CPUs.
* Given a smaller learning rate with a particular schedule, it is quite possible to train roberta for more epochs to achieve a desirable F1 score. From our findings, such a regiment would defintely warrant better compute hardware.
 
## Slide 21

* Again, to quickly recap our findings, roBERTa beat benchmarks and the support vector classifier in both macro F1 and accuracy.
* In paritcular, roberta outperformed the baseline models in classifying other and non-disasters.
* Further work can be done in balancing the datasets to improve the prevalence of other disasters, or by introducing new labels entirely to the datasets.
* We can also use stop words to improve accuracy in transformers as has been tested by other literature. Furthermore, preprocessing to handle hashtags differently such as removing the pound sign entirely or using a different tokenization algorithm to extract more feature-dense information could also be experimented on.

## Next

Here are some works we referenced and we are now open to questions.
