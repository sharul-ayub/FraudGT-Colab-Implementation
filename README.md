# FraudGT: A Simple, Effective, and Efficient Graph Transformer for Financial Fraud Detection
![framework](imgs/framework.png)

This repository holds the code for the **FraudGT framework**, a graph transformer designed for financial fraud detection.

---

## Run in Google Colab (Experimental)

This fork provides a **Google Colab–ready implementation** of FraudGT to allow users to run the model without setting up a local environment.

The goal is to make it easier to reproduce experiments and explore the FraudGT model using **GPU resources available in Google Colab**.

⚠️ Note  
The **core FraudGT implementation remains unchanged**. This repository only adds tools and documentation to run the model in a Colab environment.

### Planned Colab Features

The Colab notebook will allow users to:

- Install all required dependencies automatically
- Download and prepare the dataset
- Configure the experiment environment
- Train the FraudGT model
- Evaluate model performance

### Colab Notebook

The Colab notebook will be available here:


*(Detailed instructions and a direct Colab launch button will be added soon.)*

## Original Repository

This project is based on the original **FraudGT implementation** by the authors.

Original repository:  
https://github.com/junhongmit/FraudGT

This fork mainly adds:

- Google Colab compatibility
- simplified execution workflow
- additional documentation for easier experimentation
---

## Run in Local Machine 
## Environment Setup
You can create a conda environment to easily run the code. For example, we can create a virtual environment named `fraudGT`:
```
conda create -n fraudGT python=3.9 -y
conda activate fraudGT
```
Install the required packages using the following commands:
```
conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
conda install pyg -c pyg
pip install -r requirements.txt
```

## Run the Code
You will need to firstly specify the dataset path (`./data` in this example) and log location (`./results` in this example) by editing the config file provided under `./configs/{dataset_name}/`. An example configuration is
```
......
out_dir: ./results
dataset:
  dir: ./data
......
```
Download and unzip the [Anti-Money Laundering dataset](https://www.kaggle.com/datasets/ealtman2019/ibm-transactions-for-anti-money-laundering-aml) into your specified dataset path (for example, put the unzipped `HI-small.csv` into `./data`).
Dataset will be automatically processed at the first run.

![experiments](imgs/experiment.png)

For convenience, a script file is created to run the experiment with specified configuration. For instance, you can edit and run the `interactive_run.sh` to start the experiment.
```
cd FraudGT
chmox +x ./run/interactive_run.sh
./run/interactive_run.sh
```

