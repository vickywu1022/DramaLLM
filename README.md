# From Role-Play to Drama-Interaction: An LLM Solution

Paper: [https://arxiv.org/abs/2405.14231](https://arxiv.org/abs/2405.14231)
Demo: [https://www.bilibili.com/video/BV1sZ421x7oU](https://www.bilibili.com/video/BV1sZ421x7oU)

## 🚀 Overview

We introduce LLM-powered Interactive Drama, where players embark on a narrative journey through interactions with our Drama LLM. LLM adeptly responds in accordance with the drama script, enabling players to engage in immersive chats with characters and actively shape the story's progression through conversations and actions.

![](doc/overview.png) 

## 🕵️ Dataset: Detective Conan

Our Chinese dataset for **Detective Conan** is released now, which contains:
- Drama Script: Presents the drama story.
- Train and Test Dataset: Facillitates the training and evaluation of Drama LLMs.

### 📊 Data Statistics

The drama script consists of 11 scenes (including the prologue) and 3 endings.

Based on the script, we construct a train set with 1100 multi-turn dialogues and a test set with 130 pieces of interaction. The data type distribution is listed below:

|Type|Train|Test|
| :---: | :---:| :---: |
| Trigger by Action | - | 12 |
| Trigger by Dialogue | - | 41 |
| Plot-Related Dialogue | 884 | 41 |
| Plot-Guided Dialogue | 216 | 36 |

<!--REMARK: The train set does not contain type "Trigger by ..." as triggers serve as the last turn of each dialogue -->

### 🗂 Data Formats

Both training and testing data are stored in json files. Data from each scene is presented in the following format:

```
{
    "key": <scene_name>,
    "instruction": <drama_llm_instruction>,
    "interaction": [
        {
            "id": <data_index>,
            "type: <interaction_type>,
            "content: [
                {
                    "input": <input_text>,
                    "output" <output_text>
                },
                {
                    "input": <input_text>,
                    "output" <output_text>
                },
                ...
            ]
        }
    ]
}
```

## 🔍 Citation

```
@misc{wu2024roleplaydramainteractionllmsolution,
      title={From Role-Play to Drama-Interaction: An LLM Solution}, 
      author={Weiqi Wu and Hongqiu Wu and Lai Jiang and Xingyuan Liu and Jiale Hong and Hai Zhao and Min Zhang},
      year={2024},
      eprint={2405.14231},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2405.14231}, 
}
```

