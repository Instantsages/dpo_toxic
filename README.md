# Fine-tuning LLM for Data Defense (forked from Mechanistically Understanding DPO: Toxicity)

This repository is used for fine-tuning LLMs for data defense generation. It is forked from the repository for A Mechanistic Understanding of Alignment Algorithms: A Case Study on DPO and Toxicity. Refer to the [original repositiory](https://github.com/ajyl/dpo_toxic.git) for their code and documentation

## Training DPO

To train your own dpo model, follow these steps:

1. Install dependencies from ```requirements.txt```

2. In ```toxicity/train_dpo/train.py```, change the directory in Line 19 into your own working directory (i.e. where dpo_toxic is). In future versions we might develop better ways to do this.

3. Obtain dataset. 

- You can obtain datasets that were tested to be effective in [Google Drive](https://drive.google.com/drive/folders/1Ss44HnOuLQm38USQ9mbl3sbQY72DjD21?usp=sharing), whose access is now limited to contributors of this project.

- You can also use ```format_pickles.py``` to format datasets from pickle results from data defense experiments

4. In ```data```, make a folder named with \[name of your dataset\]. Move data (one or more .jsonl files) into the folder

5. Remember to change configurations in ```toxicity/train_dpo/config/config.yaml```. 

- Change the value ```dataset_name``` into \[name of your dataset\] (the same from step 4).

- Make sure that the name for ```model``` matches one of the model configurations in ```toxicity/train_dpo/config/model```. You can also add new folder configurations to this directory.

6. Run with ```python toxicity/train_dpo/train.py exp_name="[name of your experiment]```