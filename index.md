## SuperInsight Project

The SuperInsight open source project is a easy to use framework for finetuning GPT models.
Our goal is to provide the a collection of API so that developers can finetune their own GPT models without the hazzle of managing different packages and dependencies to train GPT models. 


### [SuperInsight FineTuning API](https://github.com/superinsight/superinsight-api-finetuning)

This is a RESTful API that you can use to setup the config and data to finetune your model

#### Stories
Stories are text will be use for finetuning. You can create unlimited number of stories using this API.
Stories can be use as dataset to finetune one or multiple models. For example, let's say that you will like to finetune a model to support french.
You can create thousands of stories and with the tag `french`, and when you are ready, you can create a French GPT model by finetuning it with all french stories. If you like to finetune a model for French and German, then you can create a finetune model by using the tags `french` and `german` so your finetune model can support both languages.

#### Finetunes
Finetunes are use to finetune and existing GPT models. This API will allow you to setup everything you need to prepare for finetuning the model. You can define your training dataset by using a collection of StoryIDs or StoryTags which will be use for dataset during finetuning. The actual training of the model happens in the superinsight-trainer-gpt repo.  

### [SuperInsight GPT Trainer](https://github.com/superinsight/superinsight-trainer-gpt)

This is a python application that continuously look for finetunes to train by calling the SuperInsight FineTuning API. After traning has been completed the model can be exported to GCP bucket defined by your environment variable.
