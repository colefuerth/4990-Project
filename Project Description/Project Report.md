# Project Description
## PART I.
### a. General Information

**Project Title:** Cloud-Based Estimation tool for Lithium Battery\
**Submitted by (insert names of team members):** Cole Fuerth, Mathew Pellarin\
**Submitted to (supervisor name):** Dr. Bala Balasingam\
**Date submitted:** November 11, 2022

### b. Project Overview: Describe the project & its purpose (300- 400 words)

A problem faced today is that most battery estimation algorithms have holes in them.

### c. Deliverables: Describe all products to be produced (200- 300 words)

A cloud database will be created to store battery data. The data that will be stored is voltage, current and temperature with its timestamp for each unique battery cell. This will be craeted in a mySQL server with the overall goal to run on a amazon web server.
Secondly, a MQTT server will be created to send data to the cloud database. The MQTT server will ensure a secure connection between the battery and the cloud database. All data will be sent to the cloud database in JSON format. 
An artificial intellagence will also be developed to analyize the data and predict the battery life, state of charge and its characteristics. The AI will be built using a neural network and be trained using the data from the cloud database. The AI will be developed using python and tensorflow.
lastly, A device that will be connected to a battery management system and will be able to log all data that the battery management system will squire. This device will be a raspberry pi with custom software that will be able to communicate with the battery management system and update the data stored on the cloud database. From the cloud database, an artificial intelligence model will be able to estimate the state of charge of the battery and its characteristics.


### d. Requirements: Describe the required resources e.g. hw/sw, technical knowledge and skills etc. (100- 200 words)

The physical hardware required for this project is a battery management system, batteries and a raspberry pi. The battery management system will ensure the batteries charge and discharge correctly as well as give us the data we need to store in the cloud database. The raspberry pi will be used to log the data from the battery management system and send it to the cloud database. 
For the software, a server with a mySQL server will be required to store the data. A MQTT server will also need to be inplace to send the data to the cloud database. A computer with python and tensorflow will be required to develop the AI. A raspberry pi with custom software will be required to log the data from the battery management system and send it to the cloud database.

The raspberry pi will be used to log the data from the battery management system and send it to the cloud database. The battery management system will be used to log the data from the battery and send it to the raspberry pi. The battery will be used to test the raspberry pi and the battery management system. The software required for this project is a MQTT server, a mySQL server and a python program that will be used to train the AI. The technical knowledge required for this project is python, mySQL, MQTT and tensorflow. The skills required for this project are the ability to work in a team and the ability to work with hardware.

The required resources are a raspberry pi, a battery management system, a battery, a MQTT server, a mySQL server, a computer with python and tensorflow installed, and a battery cell.
A strong understanding of python, mySQL, MQTT, and tensorflow is required to complete this project.



## PART II.
### 1. Risk analysis (There is no fixed format, as it will vary depending on the nature of the project. For some general guidelines please see the file under the ResourcesRisks link on BB)


## PART III. 
### 1. Work Breakdown Structure (WBS) (There is no fixed format, as it will vary depending on the nature of the project. For some general guidelines please see the file under the Resources Work Breakdown Structure (WBS) link on BB)



