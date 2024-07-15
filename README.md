# # Computer Aided Validation Team: Starter Pack
Welcome to UKAEA! UKAEA has a structure kind of like a university. The organisation is broken up into divisions, the division you are in is called the Fusion Technology Division (note that the name has changed multiple times we used to be the technology department then the fusion technology business unit and now division - you might see some of the old names on various forms). Within the Fusion Technology Division there are several different research groups, you are part of the Applied Materials Technology (AMT) group. We also work closely with colleagues in other divisions including the Advanced Computing Division and the Integrated Engineering Division.

This starter pack has three goals: 1) give you a general introduction to fusion engineering, 2) train you in software, simulation and experimental skills and 3) help you to plan your first experimental/computational project which will involve using digital image correlation to validate a model of a fusion component.

I expect that it will take some time to learn about all of these things! Not only do you need to learn about fusion engineering, you will learn about software engineering / engineering simulation as well as the latest advanced in engineering experiments. It is normal for engineers to focus on only one of these areas so take your time to gain the breadth of information needed and don't be afraid to ask for help!

## How to use this starter pack
There are a variety of resources in the starter pack including: youtube videos, journal articles, text books, guide & standards as well as hands-on computational and experimental tutorials. I would suggest two things to get the most out of it: 1) take notes and summarise what you have learned - I like to use markdown files for this but you can use anything; and 2) break up the reading with hands-on tutorials.

## First Learning Exercise
Prepare and present a ~15min powerpoint presentation that covers the following topics:
1. What is fusion and how does it work?
2. What is a tokamak?
3. What are the key engineering components of the tokamak (ignore the plasma and anything outside the cryostat)?
    - What is the function/purpose of these components?
    - What materials are they made of and why?
    - What loads and environments are they exposed to during operation?

The target audience for this presentation is your peers who might not know anything about fusion engineering. This is not an assignment and you won't be graded! The purpose of this is for you to build a mental map of fusion engineering systems so you understand your project and why you are doing it. During the presentation we will have a discussion about what you have learned to help build your understanding.

## Starter Pack Outline
Below is an outline of everything in the starter pack, you do not need to go through these in order and given the volume of information I do not expect you to read everything in detail (especially the text books and standards!). I would treat this as a source of reference material. I will indicate where it is worth reading in detail and where things are there mainly for reference or future use. All the starter pack literature can be found [here](https://ukaeauk-my.sharepoint.com/:f:/g/personal/lloyd_fletcher_ukaea_uk/EhKhp1EZDnNHg6vKUutfB8cBbtig1Y6f_gFCfBCf2Sl5yg?e=I3Cg2b).

First read this, it contains some very useful lessons on software developement and running projects in general!: https://grugbrain.dev/

1. [UKAEA](https://www.youtube.com/watch?v=TS55iTMdv3g&list=PLSWuib1HHkD_6mt9ORd6UKRlMEAOWaGkt) and [ITER](https://www.youtube.com/watch?v=kDaTQSmsJC8&list=PLgfqoaB5_JWSCm2bO37NcTfALPrBA5CC0) Youtube Channel (Fusion Specific)
    - This will give you a good general overview of fusion technology.
    - After going through these see if you can describe how a tokamak works and draw a rough sketch labelling the major components.
    - Focus on the UKAEA fusion tutorial playlist and watch the ITER ones for interest if needed.

2. [Fusion Technology Reviews](https://ukaeauk-my.sharepoint.com/:f:/g/personal/lloyd_fletcher_ukaea_uk/EnKi8j4b0zhHjZb35EQULbcBHgZZdkgkCQufYCsmjc35Fw?e=gRfsmx) (Fusion Specific)
    - Covers all the major in-vessel components and state-of-the-art designs mostly in the context of DEMO.

3. [STEP Reviews](https://ukaeauk-my.sharepoint.com/:f:/g/personal/lloyd_fletcher_ukaea_uk/EppcQ4bUtkVJig6Xzb-MhekBl7FzHID2Q6wCsW8s0jIR5A?e=K32HzL) (Fusion Specific)
    - These are long but worth going through because they give a good overview of the state-of-the-art in terms of materials and components in fusion reactors.

4. [Verification, Validation and Uncertainty Quantification Literature](https://ukaeauk-my.sharepoint.com/:f:/g/personal/lloyd_fletcher_ukaea_uk/Esh4mpnl3qtDqdNuqK1MRbgBVNKseMr2pMWxwdUmpcQzvg?e=XW3SzZ)
    - These guides outline the key theory behind simulation validation which is what we do within the team.
    - At minimum read the introductory chapters of the Oberkampf text and the ASME guide for V&V for solid mechanics models.

5. [Digital Image Correlation - General](https://ukaeauk-my.sharepoint.com/:f:/g/personal/lloyd_fletcher_ukaea_uk/EuGj1VvaTjJLuTOe1sT872IBhjiC-XGgL0seQfCtCeSqlQ?e=yIqp8W)
    - Digital image correlation is one of the main techniques we use to measure full-field component deformation.
    - Read the DIC good practice guide before and after doing the DIC training exercise.
    - The other references will make more sense once you start working with

6. Digital Image Correlation (DIC) - Video & Hands-On Tutorials
    - The main software we use for DIC is MatchID but we also use the open-source tool DICe by Sandia Labs.
    - You can find a bunch of DIC training videos on the MatchID wiki [here](https://www.matchid.eu/Wiki/doku.php?id=matchid:courses:courses)
    - The username is: AEA_YS
    - Password is: MatchID

7. [Digital Image Correlation - Model Validation](https://ukaeauk-my.sharepoint.com/:f:/g/personal/lloyd_fletcher_ukaea_uk/EvAT7APMJq1HugiM2jqWWpUBHDsnoCneAI1OMCXOY9QdrA?e=wdlh1c)
    - These are references looking at different methods for validating simulations with digital image correlation data.
    - I would read the Lava 2020 and the Rohe and Jones 2021 papers and leave the rest for future reference.

8. [New Starter Software](https://github.com/ScepticalRabbit/cav-starter-pack/blob/main/new_starter_software.md) - Hands-On Tutorials
    - Contains a bunch of information on getting started with the main software tools we use, go through all of this.

## Jargon Buster
Tokamak: a magnetic confinement fusion reactor (I like to call it a donut shaped sun in a magnetic bottle).

JET (Joint European Torus): Currently the largest operational tokamak, holds several international fusion records. Based in the UK at the UKAEA Culham site but is being decommissioned within a year.

ITER (International Thermonuclear Experimental Reactor): Successor to JET,
a large international collaboration to build an experimental tokamak in France.
The goal is to increase power output (Q) and test breeder blanker technologies.

STEP (Spherical Tokamak for Energy Production): This is a UKAEA program that
you will hear about frequently. The plan is to build a plant capable of net
power output to the grid complete by 2040.  You will also see SPP (STEP Prototype Plant) and SCP (Step Commercial Plant).

DEMO (DEMOnstration power plant): The proposed successor to ITER capable of
outputting net power out to the grid by 2050. You will most often hear of
EU-DEMO which UKAEA has active participation in.
