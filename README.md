# Deep-Learning-notes
Take notes on learning Deep Learning

## Topics
* Underfitting
* Overfitting
* categorical_crossentropy VS. sparse_categorical_crossentropy


## Sections
### Underfitting
#### How do you know if your model is underfitting?
Your model is underfitting if the accuracy on the validation set is higher than the accuracy on the training set. Additionally, if the whole model performs bad this is also called underfitting. For example, using a linear model for image recognition will generally result in an underfitting model. Alternatively, when experiencing underfitting in your deep neural network this is probably caused by dropout. Dropout randomly sets activations to zero during the training process to avoid overfitting. This does not happen during prediction on the validation/test set. If this is the case you can remove dropout. If the model is now massively overfitting you can start adding dropout in small pieces.


### Overfitting
#### How do you know if your model is overfitting?

Overfitting happens when your model fits too well to the training set. It then becomes difficult for the model to generalize to new examples that were not in the training set. For example, your model recognizes specific images in your training set instead of general patterns. Your training accuracy will be higher than the accuracy on the validation/test set. 




#### So what can we do to reduce overfitting?

Steps for reducing overfitting:
1. Add more data
2. Use data augmentation
3. Use architectures that generalize well
4. Add regularization (mostly dropout, L1/L2 regularization are also possible)
5. Reduce architecture complexity.



### categorical_crossentropy VS. sparse_categorical_crossentropy
#### What are Loss Functions?
A loss function (or objective function, or optimization score function) is one of the three parameters (the first one, actually) required to compile a model:
```
model.compile(loss='categorical_crossentropy', # <== LOOK HERE!
              optimizer='adam', 
              metrics=['accuracy'])
```

#### Difference
If your targets are one-hot encoded, use categorical_crossentropy.  
Examples of one-hot encodings:
```
[1,0,0]  
[0,1,0]   
[0,0,1]  
```
But if your targets are integers, use sparse_categorical_crossentropy.  
Examples of integer encodings (for the sake of completion):  
```
[1,2,3]
```

## Reference
Thanks to those great writers/ instructors/scholars   
[Deep Learning #3: More on CNNs & Handling Overfitting][001], Rutger Ruizendaal   
[categorical_crossentropy VS. sparse_categorical_crossentropy][002], Jovian Lin, Ph.D.  
[VIP cheatsheets for Stanford's CS 229 Machine Learning][003], Afshine Amidi and Shervine Amidi  
[VIP cheatsheets for Stanford's CS 230 Deep Learning][004], Afshine Amidi and Shervine Amidi





<!--
Link reference:
-->
[001]: https://towardsdatascience.com/deep-learning-3-more-on-cnns-handling-overfitting-2bd5d99abe5d
[002]: https://jovianlin.io/cat-crossentropy-vs-sparse-cat-crossentropy/
[003]: https://stanford.edu/~shervine/teaching/cs-229.html
[004]: https://stanford.edu/~shervine/teaching/cs-230.html
