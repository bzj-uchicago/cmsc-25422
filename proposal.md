# Project Title

Reproducing nPrintML for Snowflake Fingerprintability

## Project Participants

Format the following information in a markdown table:

* First Name, Last Name
* Email Address
* Project Role

| First Name, Last Name | Email Address | Project Role |
|---|---|---|
| Brian, Jiang | bzj@uchicago.edu | Project and Evaluation Lead |
| Ashwin Balaraman | abalaraman1@uchicago.edu | Network Data and Feature Engineer |
| Justin Wang | justinzw@uchicago.edu | Machine Learning Engineer |


## Project Description

One paragraph description of your project. Summarize the following:
* Problem statement
* Why it is important problem
* How it relates to the theme of the course (e.g., what is the intersection
  with networking and ML?).
* Any related work you are aware of
* What is the goal? Research? Tech transfer? Reproducing a result?

Snowflake is a Tor pluggable transport that uses WebRTC to help users bypass
Internet censorship, but its intended indistinguishability from ordinary
WebRTC services may not hold under machine-learning-based traffic analysis.
This project will investigate whether encrypted DTLS handshakes can reveal
whether traffic belongs to Snowflake, Facebook Messenger, Google Hangouts, or
Discord, while also identifying the browser used to generate the traffic. This
is important because successful fingerprinting could weaken the privacy and
censorship-resistance benefits of Snowflake, while reliable classification
could also help researchers understand the limits of encrypted traffic
obfuscation. The project directly connects networking and machine learning by
converting packet captures into nPrint/pcapML feature representations and
training classifiers to identify network applications without inspecting
payload contents. We will reproduce the Snowflake-related experiment from
Holland et al.'s paper, *New Directions in Automated Traffic Analysis*, and
its corresponding nPrint benchmark. Our goal is replication: we will follow
the published data, feature, model, and evaluation procedure as closely as
possible and report whether we obtain comparable results. 


## Data

* What data will you need to complete this project?

We will use the dataset from the nPrint website available here (https://drive.google.com/file/d/1QYPXemuoU7obtJZdL3MAmIxgFLraR0S8/view). 

## Machine Learning

We will use nPrint to convert the packet captures into a unified packet
representation and nPrintML with AutoGluon to train the classifier, following
the procedure from *New Directions in Automated Traffic Analysis*. As a
baseline, we will use a majority-class classifier that always predicts the
most common label. Our primary model will be the paper's automated
machine-learning model, with its preprocessing and configuration reproduced as
closely as possible.

## Evaluation

We will use the paper's training and test split procedure as closely as
possible, keeping the test set held out until the final evaluation. We will
report macro F1 as the primary metric because it is the benchmark's target
metric, along with accuracy, per-class precision and recall, and a confusion
matrix. We will compare our reproduced result with the result reported by the
paper and document any differences in software versions, configuration, or
runtime.

## Learning Objective

We expect to learn how nPrint represents encrypted network traffic, how nPrintML
uses AutoML for network classification, and how to reproduce a published
machine-learning result. We will also learn how the train/test split and choice
of evaluation metric affect conclusions about traffic-classification
performance.

## Deliverables

* Detail what you intend to turn in for the final project. (Refer to the documentation about the project to outline your deliverables.)

Reproducible code and instructions for downloading the dataset, generating nPrint features, running nPrintML, and evaluating the classifier

A final report documenting the paper's method, our implementation choices, software environment, runtime, and reproduced metrics

A comparison between our results and the results reported in *New Directions in Automated Traffic Analysis*, including an explanation of any differences

A presentation describing the original method and the outcome of our reproduction
