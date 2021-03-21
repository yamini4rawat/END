# END - Capstone Project - Build Pyton Code Generator from English Sentence


## Python Embeddings

1. Used Pytorch Open source code as input for Python keywords embedding. Performed initial data cleaning and replaced new lines with "/n" and tabs with "/t" .
2. Trained using Glove Embedding code that was shared as input as part of session 13. Once embeddings were trained. Created a custom python embedding file  as shown in the image below.

![](https://github.com/deepak121993/END/blob/main/END%20Capston/Custom%20Embedding%20File.jpg)

3.  Custom Python embedding is loaded to the training for target field as below.

   ![](https://github.com/deepak121993/END/blob/main/END%20Capston/Custom%20Embedding%20File_new.jpg)

## Data Cleaning

- Wrote scripts to ensure that tabs, line breaks, semicolon are used when necessary and appropriately.
- Converted all line breaks to /n and all tabs to /t so that they are learned as part of the training and the system knows when to use them. 

## Training 

- Used a transformer model with following specifications for training:

  | Item                 | Details                             |
  | -------------------- | ----------------------------------- |
  | Architecture         | Transformer                         |
  | Number of Layers     | 6 Encoder and 6 Decoder layers      |
  | Learning Rate        | 1e-4                                |
  | Batch Size           | 64                                  |
  | Epochs               | 100                                 |
  | Dropout              | 0.1 for Encoder and 0.1 for Decoder |
  | Attention Heads      | 8 for Encoder and 8 for Decoder     |
  | Trainable Parameters | 9,349,165                           |
  | Loss                 | Training - 0.704 Validation - 1.661 |
  | PPL                  | Training - 2.021 Validation - 5.264 |
  | Loss Function        | CrossEntropy.                       |

  - Initially trained with English embeddings for both Source and Target and got decent results. But In the quest to improve the accuracy, had used Python Embeddings as mentioned above for the Target field. 

  - The accuracy improved by a small percentage but the training converged faster.

  - Below are Examples of few queries and the outputs. Some of the output are very inaccurate. I think need to cover more examples and go for a larger training corpus to improve accuracy in addition to using a better loss function.

   
    
    

### Conversion and output Attention for one of the examples.

![](https://github.com/deepak121993/END/blob/main/END%20Capston/download.png)

## Conclusion

The model is learning. But some postprocessing required to get the desired output.

- identifying when to write a function and when to write a script based on the question. It looks for the word ***write a function*** to <u>write a function</u> and ***write a code*** to <u>write a script</u>.
- The usage of semicolon and tabs.

But Logically the output function isn't accurate and can be improved by :

- Bigger  training set .Better loss function.
- Using improved Python keyword embeddings trained on larger corpus and more number of epochs.

### Thanks to Rohan and Zoheb for this awesome course. Although not able to complete this project properly.Trying to grasp new concepts of transformers and deep learning NLP.
### Looking forward to END Phase 2.
