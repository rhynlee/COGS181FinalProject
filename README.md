# About

This was a final project concerning the application of deep learning on a dataset using pytorch as taught in the course at UCSD.
Data was taken from kaggle: https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia

Three state of the art pretrained computer vision models at the time, Resnet101, Densenet161, and VGG19, were fine tuned on this dataset containing chest x-rays for identification of pneumonia. These models were tested once with a Stochastic Gradient Descent optimizer (SGD) and once again with an adapative learning rate optimizer (Adam).

# Results
The best performing model reaches a precision of .89 on the dataset with a model that's only 100MB in size (DenseNet161) using the Adam optimizer. This may be interpreted in layman terms as that the model has a 89% chance to determine that an x-ray is from a patient with pnuemonia if the patient has pneumonia. Consequently, it has a 11% chance of misdiagnosing that a x-ray from a patient without pneumonia has pneumonia.

# Takeaways

Deep learning has untapped potential for medical purposes. In a sense, there is likely a medical analog to the Kasparov Principle in chess:

"The full "Kasparov Principle" isn't simply that human+machine > machine or human, but that human+machine+superior process is the key." (https://twitter.com/Kasparov63/status/733365798169923584)

Finding this superior process is key, as it is likely legal and ethical issues surrounding the case of a machine getting a medical diagnosis wrong that prevents it from being used on a wide scale. In the worst case, this would lead to futher complications or death begging the question who is liable? Issues as they may be, it's undeniable that the use of machine learning to streamline diagnosis has potential to enable more widespread healthcare. Making diagnosis easier on medical professionals enables them to handle more patients. This becomes especially important in developing countries which lack a widely functioning healthcare system as fewer personnel would be needed to administer medical procedures.

On the deep learning side, this project demonstrated first hand that larger models may end up producing only incremental gains. The 500MB VGG19 model does not particularly perform noticeably better than the 100MB DenseNet showing that cost/performance should be taken into consideration. An illustrated example would be that the same amount of memory would be able to load five DenseNet models in the place of one VGG19 model. Thus taking the model that has the best perfomance on academically renowned benchmarks/datasets can often be unwise when moving over to practical applications. The other takeaway from this project is that adaptive learning rates demonstrably outperforms traditional stochastic gradient descent. It has been well known at the point that adding a sort of momentum to the size of changes the model makes to itself increases performance, but it was nice to be able to confirm it first hand.
