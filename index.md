# Dennis Triepke Data Science Portfolio (WIP)

This is a collection of some of my Data Science projects for learning and growing.  

## [Text-based Graph Convolutional Network with tensorflow 1.x](https://github.com/dtriepke/Graph_Convolutional_Network)
- Created the GCN model from the paper  [Graph Convolutional Networks for Text Classification](https://arxiv.org/pdf/1809.05679.pdf)  
- Trained and tested the model with IMDB movie review sentiment classification dataset in a Semi-Supervised approach
  
![](gcn_propagation_equation.png)
![](GCN.png)


## [NLU Model Selection App](https://github.com/dtriepke/nlp_model_selection_app)
NLU has created a powerful API for embeddings (and even some NLP downstream-task like sarcasm detection or sentiment classification) in 1-liner of code. However, at the beginning of each NLP projects, you are facing the issue of selecting the model that fits best to your data structure. This app is designed for selecting and comparing pre-trained NLP models from NLU (John Snow Lab) with own data. Whether your project has word, sentence or document embeddings: upload the data, select some pre-trained models and download the embeddings. 

- Model Selection Word Embedding  
- Model Selection Sentence or Document Embedding
- Fake News Classifier

![](landing_page.png)
![](word_embedding_page.png)

## [Deep Q-Learning (Mountain Car)](https://github.com/dtriepke/Deep_Q_Learning_MountainCar)

This code was designed associated with my master thesis,
"Aspects of Sequential Decision Making Reinforcement Learning and Bandit Problem", Institution for Mathematical Stochastics, Otto-von-Guericke-Universität, 2019. 


The project is about solving a reinforcement problem with an Deep Q-network agent based on the paper et al. Mnih, "Human-level control through deep reinforcement learning", Nature 2015.


### Game Environment

The playbox from `openAI` for developing and comparing reinforcement learning algorithms is the library called `gym`.
This library includes several environments or test problems that can be solved with reinforcement algorithms. 
It provides natural shared interfaces, which enables to skip the complex manual feature engineering. 


This project captures the learning problem `MountainCar`. 
Here is the challenge that a car, stocked between two hills, need to climb the right hill, but a single impulse causes a to less momentum. The only way to solve the problem is that the agent drives front and back in order to generate a stronger momentum. 
Moore first described the problem in his PhD thesis: "Efficient Memory-Based Learning for Robot Control", University of Cambridge, 1990.

<img width="699" alt="image" src="https://user-images.githubusercontent.com/28724974/174587587-a3a1830a-008f-4778-af6c-01f4fd438b34.png">

This is the `MountainCar` evironment from gym.


The spaces for the action is disrcet and there are 3 possible actions availible.


number | action  
-------|-------  
0      | push left
1      | no operation
2      | push right


The observation is an `2` dimensional vector. The first dimension tells the position of the car and the second the velocity.

number | sate      | vakues
-------|-----------|------------  
i_1t   | position  | [-1.2, 0.6]
i_2t   | velocity  | [-0.07, 0.07]


### Reward 

- The original reward is set to be -1 for each time step except the goal position of 0.5 is reached.

- The mutated reward is adjusted to be i_1t appart from the goal state. Here is the reward set as 10. 


### Terminal State
The terminal state determnines the end of an epsiode and is either the state at time 500 or the the goal state at position 0.5.
