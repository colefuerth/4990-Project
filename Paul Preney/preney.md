# Paul Preney C++ for Supercomputers

Friday September 30, 2022

## introduction

- paul is the sharknet representative on campus
- undergrad in bio and cs (double major), consulting in industry and then a masters in CS
- unofficially involved in starting sharknet canada for high performance computing
- after his masters he was one of thirteen called the digital research alliance of canada
- the xsede program is a national program that provides access to supercomputers in the united states

## grief over security

- the uni security is called draconian and paul hates it so so much
- we are a target for hacking because of our research and resources

## pauls background

- today, provides support for people doing high performance computing
- includes cloud and storage services
- storage is done through special applications

## SHARCET

- SHARCNET is a Shared Hierarchal Academic Research Computing Network
- at computeontario.ca
- it is an association of 19 universities and colleges in canada
- toronto is the only one in canada with its own, called SciNet
- as long as you're in the country you should have access to some of these resources
- you can get federal or provincial grants to use these resources
- as long as the admin is part of the canadian association, even if your team is in the states, you can use these resources
- compute canada is **free** to canadian researchers with PIs reporting research activities to compute canada
- **undergrad level coursework is not allowed on these computers**

## Specs

Specs can be found on [alliancecan.ca](http://docs.alliancecan.ca/wiki/Graham) for the graham supercomputer

- This also details file transfer protocols for sending your data to and from the cluster for processing
- This cluster is completely liquid cooled and is FULL of SSDs

## using the cluster

*you can log in to jupyter hub on the graham server for research*

[https://jupyterhub.sharcnet.ca](https://jupyterhub.sharcnet.ca)

**this is where curtis' icpc compiler for the bio thing came from**

There are a few hundred modules you can utilize when you login to the cluster, so like icpc, gcc, python, etc.

- DO NOT run jobs on the login node, you will get a warning and tehy will kill your job
- don't queue jobs requiring too many resources, it will take longer in the queue before it runs
- less requirements means it will run earlier

## Typical applications

- fluid dynamics
- finite element analysis
- molecular dynamics
- bioinformatics
- astrophysics
- weather forecasting
- stock market analysis
- machine learning
- movie making

## timing

- you can approximate time taken for a job by doing timings on calculations and writes and estimate the time taken
- you want to inflate your time when you submit the job, so you don't get killed
- if your time runs out your job is killed and resources are freed, so you want to checkpoint your job periodically

## priority

- priority is by research team
- also depends on time or resources
- you need to choose a core count, gpu resources, ram requirements, and time

## post notes

- on his ECC workstation, you actually lose ram speed as you increase in size (like big amounts, he has 512gb)
- you need to intentionally take advantage of caching and stuff like that
- always have jobs waiting in the queue when you are doing research so something is always happening
- don't do long term calculations in parallel on a laptop, you need server class hardware to run full tilt nonstop. laptop thermals are only meant to work hard in bursts and the thermals will fail if it needs to work for days on end
