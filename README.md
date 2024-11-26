# DLCV Final Project

# How to run your code?
* TODO: Please provide the scripts for TAs to reproduce your results, including training and inference. For example, 

```
bash train.sh <Path to gt image folder> <Path to annot file>
bash inference.sh <Path to gt image folder> <Path to annot file> <Path to predicted file>
```

You can add more arguments to the script if you need.

# Usage
To start working on this final project, you should clone this repository into your local machine by the following command:
```
    git clone https://github.com/DLCV-Fall-2024/DLCV-Fall-2024-Final-2-<team_name>.git
```  
Note that you should replace `<team_name>` with your own team name.

For more details, please click [this link](https://docs.google.com/presentation/d/1Vvhq1-QW2J5xuf6PNpZ9UshkfXhp3tmI02334JrfYZs/edit?usp=sharing) to view the slides of Final Project - .Multimodal Perception and Comprehension of Corner Cases in Autonomous Driving **The introduction video for final project can be accessed in the slides.**

After cloning the repository from GitHub, the folder structure should be like this:
```
CODA-LM/
└── few_shot/
│   ├── scene_few_shot/
│   │   ├── high.json
│   │   └── low.json
│   └── suggestion_few_shot/
│       ├── high.json
│       └── low.json 
└── gemini_eval.py
└── llama_eval.py
└── scorer.py
└── requirement.txt
...
```

# Environment Setup
1. Create a new environment
```
conda create -n <your_env_name> python=<python_version>=3.10>
conda activate <your_env_name>
pip install -r requirement.txt
```
2. Install Gemini API: To install Gemini API, please refer to the following command. For more details, please refer to [Gemini API](https://ai.google.dev/gemini-api/docs/quickstart?hl=zh-tw&_gl=1*ciqklc*_up*MQ..&gclid=Cj0KCQiAgJa6BhCOARIsAMiL7V8rppSkxxeqt-eVsCczUZ8Iz2mXXiTi1EkuP7K2xalpBYOk9HLgbv0aAqAIEALw_wcB&lang=python).
```
pip install -q -U google-generativeai
```
3. You can install any additional packages you need for you final project.

# Dataset

for each data,
```
{"id": , "image": PIL image, "conversations": []}
```

# Evaluation
we provide two evaluation scripts
1. `Gemini evaluation`: this file is identical to the one we used in Codalab
```
python3 gemini_eval.py --prediction <you predicted json file> --api_key <your gemini api key>
```
2. `Llama evaluation`: Since Gemini API has daily usage limits for free accounts, we provide a local testing option using LLaMA-3 as the LLM base model. Note that using llama_eval.py requires approximately 16GB of GPU memory.
```
python3 llama_eval.py --prediction <you predicted json file>
```
Both files will return the LLM judges and BLEU score of your predicted json file.
```
Genral score: x.xx
Reasoning score: x.xx
Suggestion score: x.xx
LLM judges: x.xx
BLEU_1 score: x.xx
BLEU_2 score: x.xx
BLEU_3 score: x.xx
BLEU_4 score: x.xx
```

# Submission Rules
You need to submit your predicted json file to the following link: [Codalab]()

You can submit up to `5` times per day.

### Deadline
113/12/26 (Thur.) 23:59 (GMT+8)
    
# Q&A
If you have any problems related to Final Project, you may
- Use TA hours
- Contact TAs by e-mail ([ntudlcv@gmail.com](mailto:ntudlcv@gmail.com))
- Post your question under `[Final challenge 1] Discussion` section in NTU Cool Discussion

