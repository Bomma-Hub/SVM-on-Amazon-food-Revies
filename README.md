# SVM-on-Amazon-food-Reviews


Support Vector Machines:

	It can be used for both classification and regression.
	Base point : A plane that separates both positive and negative points as widely as possible.
	The difference between the distance from positive and negative values/classes to the threshold plane is called Margin(when misclassifications are not allowed).
	If we are using the threshold that gives the largest margin to make classifications then it is called Maximum Margin Classifier.
 
 
  


	When misclassifications are allowed then the distance between the observations and threshold is called Soft-Margin. 
 
 
 
    
 
 
 




 


For Reference :
https://www.youtube.com/watch?v=efR1C6CvhmE



 


 
 
 
 


Mathematical Derivation:

 


Let   (W.T * x + b =0) is our plane (decision surface) and Support vector planes be W.T * x+ b= 1 and W. T * x + b= -1.
	The distance between the two support vector planes will be the Max Margin around the decision surface plane.
	Margin distance (d) = 2 / || W || (l2 norm).
	Our aim is to maximize the distance between the support vectors.
i.e 	(W*,b*) = argmax w,b ( 2 / || W || ). 
S.t   Yi (W.T * Xi+b) >= 1 for all ‘i’.
The above condition satisfies only if data is linearly separable. Also called “Hard Margin” as we are strictly dependent on constraint.

Soft Margin:
	When misclassifications are allowed then the distance between the observations and threshold is called Soft-Margin

For correctly classified points y (W.T * X + b) >=1
For wrongly classified pts Y (W.T * X + b ) = 1 – ꜫ 
Equation of soft Margin:
(W*,b*) = argmax w,b ( 2 / || W || )  = argmin ( || W ||/ 2  + 1/n * sum(ꜫ i  ))
For all ‘i’
S.t   Yi (W.T * Xi+b) >= 1 - ꜫ i   for all ‘i’
ꜫ i   >=0
We can interpret softmargin equation as ( regularizer + loss)
(Loss)  : 1/n * sum(ꜫ i  )  --------------- > Avg. distance for miss-classified points.

Dual Form of SVM :
Max ∑_(i=1)^n▒αi – ½ ∑_(i=1)^n▒〖∑_(j=1)^n▒αj αiyiyjxi.T xj〗

Xi.T * Xj  represents similarity.
Kernel trick is a function to calculate similarity
Radial Basis Finction:
	This Kernel is used in SVM to get the similarity of the points/vectors.

RBF kernel eq:  K( x1 , x2 ) = exp( -  (||x1-x2 ||)^2/2σ^2) 

Where   ‘σ^'   is hyperparameter and ||X1-x2||^2 is distance between two points.

	Distance : 
|| x1-x2 ||^2 = (d12 )^ 2  increases then k(x1, x2) decreases.
	 
	‘σ^' : 

 
 
How SVM is related to KNN ?
How polynomial kernals are equivalent to feature tranformations ?
What is Huber loss ?


CallibratedclasifierCV(calibrating the probabilities) :
Steps:
	Predicting Probabilities
	Calibration of Predictions
	How to Calibrate Probabilities in Python
	Worked Example of Calibrating SVM Probabilities

Reference: https://machinelearningmastery.com/calibrated-classification-model-in-scikit-learn/
