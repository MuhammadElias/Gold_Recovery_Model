# Gold_Recovery_Model

## Intoduction:

In this project, we will be developing a prototype of a machine learning model for Zyfra, a company that specializes in providing efficiency solutions for heavy industry. The goal of this project is to predict the amount of gold recovered from gold ore, using data on extraction and purification processes. By optimizing production and eliminating unprofitable parameters, this model will help improve efficiency in the gold extraction process.

To achieve this, we will need to prepare the data, perform data analysis, and develop and train a machine learning model. The documentation from pandas, matplotlib, and sklearn will be utilized throughout the project.

By understanding and analyzing the stages of the gold extraction process, such as flotation and purification, and considering parameters such as rougher feed, reagent additions, and various technological and stage-specific factors, we aim to create a robust machine learning model that accurately predicts the amount of gold recovered from gold ore.



## Technological Process
How is gold extracted from ore? Let's look into the process stages.
Mined ore undergoes primary processing to get the ore mixture or rougher feed, which is the raw material for flotation (also known as the rougher process). After flotation, the material is sent to two-stage purification.


Let's break down the process:

1. Flotation

Gold ore mixture is fed into the float banks to obtain rougher Au concentrate and rougher tails (product residues with a low concentration of valuable metals).

The stability of this process is affected by the volatile and non-optimal physicochemical state of the flotation pulp (a mixture of solid particles and liquid).

2. Purification

The rougher concentrate undergoes two stages of purification. After purification, we have the final concentrate and new tails.

## Data description

Technological process

- Rougher feed — raw material
- Rougher additions (or reagent additions) — flotation reagents: Xanthate, Sulphate, Depressant
 - Xanthate — promoter or flotation activator;
 - Sulphate — sodium sulphide for this particular process;
 - Depressant — sodium silicate.
- Rougher process — flotation
- Rougher tails — product residues
- Float banks — flotation unit
- Cleaner process — purification
- Rougher Au — rougher gold concentrate
- Final Au — final gold concentrate


Parameters of stages

- air amount — volume of air
- fluid levels
- feed size — feed particle size
- feed rate


## Feature naming

Here's how you name the features:

[stage].[parameter_type].[parameter_name]

Example: rougher.input.feed_ag

Possible values for [stage]:

- rougher — flotation
- primary_cleaner — primary purification
- secondary_cleaner — secondary purification
- final — final characteristics


Possible values for [parameter_type]:

- input — raw material parameters
- output — product parameters
- state — parameters characterizing the current state of the stage
- calculation — calculation characteristics


## Evaluation metric
To solve the problem, we will need a new metric. It is called sMAPE, symmetric Mean Absolute Percentage Error. 

It is similar to MAE, but is expressed in relative values instead of absolute ones. Why is it symmetrical? It equally takes into account the scale of both the target and the prediction.

We need to predict two values:

rougher concentrate recovery rougher.output.recovery
final concentrate recovery final.output.recovery