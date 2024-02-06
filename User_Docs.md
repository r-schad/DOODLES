# DOODLES User Docs
## Quick Start
### Pre-Requisites
Python 3.9 installed on your machine.
Code editor (such as VS Code, PyCharm, etc.) installed on your machine.
### Installation Steps
Using the DOODLES project to generate a Self-Organizing Map (SOM) of doodles is simple. To use the code, follow these steps:
1. Clone the repository located here: https://github.com/r-schad/Code-Ring-Network/tree/main
2. Install all packages listed in requirements.txt using the command `pip install -r requirements.txt`.
3. The main() function is located in Code_Ring_Network.py. There, you can edit model parameters and training settings (see the next section for a description of the training settings).
4. Run Code_Ring_Network.py
### Training Settings
There are two main training functionality settings that can be toggled in the train() parameters:
1. show_results - When True, the activity plot of the Ring Layer and the corresponding doodle are outputted in a separate plot for each iteration of the training process. When False, no plots are generated, outside of those listed in the next section. Note: enabling show_results slows training time by about 80%. 
3. plot_gif - When True, a GIF video of the doodling process is generated for each output. When False, no GIFs are generated for any part of the training. Note: enabling plot_gif severely cripples training speed, and should only be used for a few iterations.
### Description of Outputs
There are a variety of outputs generated from each run of Code_Ring_Network.py. A folder inside the current directory will be created for each run, named by the datetime string of the time of running. Inside that folder, each outputs for the current run will be stored. The outputs come in the form of the following files:
1. Maps: each neuron in the map layer is activated, and the corresponding doodle output is placed on the neuron's location in the map. The Map plots are generated before and after training, and every 100 epochs throughout training.
2. Weights: the weight matrix between the Map and Code Layers is plotted as a heatmap. Again, these plots are generated before and after training, as well as every 100 epochs.
3. Scores Heatmap: the metric score with each map neuron generating the activity across each epoch is plotted. So, the rows of the heatmap are the neuron generating the activity, and the columns are each epoch over time. Note that the scores generated at the beginning of training are hardly due to the activity of the map layer; rather they are a result of the strong noise signal causing the exploration of the model during inital training stages.
4. Scores Plot: the scores of each neuron are plotted over the epochs. The average epoch score throughout training is plotted in black.
5. Parameters List: the list of all local variables are stored in the params_id.txt file, where id is the datetime string of the current run. These local variables include all model parameters necessary to replicate (with the exception of random effects) the current trial.
   
