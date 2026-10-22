# Text Classification using pre-trained Word Vectors
This repository contains the code for text classification using recurrent neural networks and glove pre-trained vectors.

### Dataset
The [dataset](https://catalog.data.gov/dataset/consumer-complaint-database) is a collection of complaints about consumer financial products and services that we sent to companies for response. The actual text of the compalint by the consumer is given in the `Consumer complaint narrative` column. The dataset also has a `product` column which contains the product for which the consumer is raising the complaint. We are going to build a model to predict the product given the complaint text. 

### Running on your system locally
 
To run the notebook on your local system set up a [python](https://www.python.org/) environment. Set up the [jupyter notebook](https://jupyter.org/install) with python. Download the notebook and open a jupyter notebook to run the code on local system.
 
The notebook can also be executed by using [Visual Studio Code](https://code.visualstudio.com/), and [PyCharm](https://www.jetbrains.com/pycharm/).

**Python Version: 3.8.10**

The Python 3.8.10 version is supported for the execution of this project.
1. Running the codes locally: Python 3.8.10
    - Create a virtual environment: In the terminal or command prompt, use the following command to create a new virtual environment:

        - For Windows:
            `py -3.8 -m venv env`

        - For macOS and Linux:
            `python3 -m venv venv`
        This command creates a new virtual environment named "venv" in the current directory.

    - Activate the virtual environment:

        - For Windows (Command Prompt):
            `venv\Scripts\activate`


        - For macOS and Linux (Terminal) :
            `source venv/bin/activate`
    
Once the virtual environment is activated, you should see the environment name (e.g., (venv)) in the terminal or command prompt.

- Install project requirements: With the virtual environment active, you can now install the required packages for your project. Typically, the required packages are listed in a requirements.txt file. Make sure you have the requirements.txt file for your project.

2. Setup the pip and installing dependencies in Virtual environment

    - Upgrade pip
        `python -m pip install --upgrade pip`

    - To install the requirements, use the following command:
        `pip install -r requirements.txt`



### Preprocessing the data
To pre-process the data and the embeddings, run:
```
python precessing.py
```

### Train the model
To train the model using RNN, run:
```
python Engine.py --model_type rnn
```
To train the model using LSTM, run:
```
python Engine.py --model_type lstm
```

### Predictions
To make prediction on a new review, run:
```
python predict.py --test_complaint "I am a victim of Identity Theft & currently have an Experian account that I can view my Experian Credit Report and getting notified when there is activity on my Experian Credit Report. For the past 3 days I've spent a total of approximately 9 hours on the phone with Experian. Every time I call I get transferred repeatedly and then my last transfer and automated message states to press 1 and leave a message and someone would call me. Every time I press 1 I get an automatic message stating than you before I even leave a message and get disconnected. I call Experian again, explain what is happening and the process begins again with the same end result. I was trying to have this issue attended and resolved informally but I give up after 9 hours. There are hard hit inquiries on my Experian Credit Report that are fraud, I didn't authorize, or recall and I respectfully request that Experian remove the hard hit inquiries immediately just like they've done in the past when I was able to speak to a live Experian representative in the United States. The following are the hard hit inquiries : BK OF XXXX XX/XX/XXXX XXXX XXXX XXXX  XX/XX/XXXX XXXX  XXXX XXXX  XX/XX/XXXX XXXX  XX/XX/XXXX XXXX  XXXX XX/XX/XXXX" --model_type lstm
```