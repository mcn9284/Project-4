# **Using Neural Networks to Diagnose Pneumonia**

# **Summary**
We develop a classification model that uses a training set of chest x-rays to discern features and patterns of features that characterize the presence of pneumonia in hospital patients. The model is developed as part of a suite of deep learning automated diagnostic feature of a new line of state-of-the-art portable X-ray machines. Using the Keras library's extensive convolutional neural network toolset, we train increasingly complex classification models on a known dataset. While striving for the greatest possible accuracy, we are also keen to minimize the number of false negatives our final model outputs. We accomplish this through modifications in model depth, number of filters, regularization techniques, and tuning various hyperparameters in optimization. The resulting model achieved a 94.80% accuracy score

# **Business Problem**
A small regional chain of hospitals has been given a grant to be used to update their radiology department's equipment. I will be representing a medical imaging device company whose latest product includes an ambulatory (portable) X-Ray machine with an automated 'diagnostic assistance' program that utilizes deep learning to process the X-ray images and alert on potential health issues present. In this case, I walk the board of directors through the device's success in detecting pneumonia. After a brief, accessible overview of how it does this and its accuracy, I present detail the ways in which such technology creates an efficient, cost-effective, and potentially adaptable/expandable solution to patient complaints of lengthy waits and missed diagnoses.

# **Data Understanding**
The Xray images were provided by Guangzhou Women's and Children's Hospital in Guangzhou, China. They are nearly 6,000 radiographs of pediatric patients, of which most are labeled as positive for pneumonia. They are all jpeg images with personally identifying information scrubbed from the metadata. The imbalance in class is on the order of 75% pneumonia, 25% normal. This is corrected for in the model fitting sections by assigning weights.

# **Methods**
This is an image processing binary classification task. We began with a bare bones CNN (consisting of one conv2d and maxpool layer, one fully connected layer, and a one unit sigmoid classifier. Each iteration of the model seeks to increase complexity--and the model's ability to generalize--while at the same time keeping a check on overfitting. The overall architecture is inspired by the VGG16/19 architecture which employs blocks of consecutive conv2d layers before a pooling layer. Each block has increasing numbers of filters, and all are ReLu activated. 
To combat overfitting, we mainly employ l2 kernel regularizers in the final conv layer(s) and after the flattening layer. 
Each model is defined with the binary-crossentropy loss function and Adam optimized with learning rates that start at 0.0001 and finish at 0.00001.
While seeking to maximize accuracy, we were also keeping any eye on minimizing false negatives.

# **Results**
Many of the models displayed signs of overfitting, some worse than others, and many validation and test learning curves were very jittery. Our most successful model--cnn7, ended up with a test accuracy of 95%, and with precision and recall values of 95% and 97% respectively...indicating the model was quite good at distinguishing between positive and negative classes on image data it had yet to see.

# **Recommendations**
The diagnositc algorithm yields reliable enough results that patients with suspected pneumonia could be rapidly screened at intake by just about anyone trained to use the machine. Of course, an experienced radiologist or doctor should always review cases, but automated and rapid screening is both money-cost effective and time-cost effective at busy hospitals, particularly with respiratory illness season in full swing all around us. 

The algorithm could also use new patient xrays to further train itself to further bolster its ability to discern the features of pneumonia and provide an accurate diagnosis.

# **Contact**
For more information, or for questions and comments, I can easily be reached via email at mcn9284@gmail.com
Thank you!
Matthew Noonan


# **Repo Structure**
├── images
├── .gitignore
└── project_4_notebook_final.ipynb
├── README.md
├── project_4_presentation.pdf
