---
layout: page
title: Syllabus 
permalink: /syllabus/
---
* toc 
{:toc}

## Course Information
Title: Special Topics -- State Estimation for Robotics and Autonomous Systems\
Number: MECH 4395/5390\
CRN: \
Term: Fall 2025\
Instructor: John Bird\
Office: Engineering Building A-115\
Instructor email: jjbird@utep.edu\
Instructor phone: 915.747.8406\
Office Hours:\
TBD

### Course Description
State estimation is concerned with determining the internal states of a system by combining sensor measurements. Estimation is fundamental to many mobile robotics, aerospace, and process control systems. In this course we will study basic probability and system theory underlying estimation, techniques to determine if a state can be estimated from available observations, and state estimation algorithms for linear and nonlinear systems.

### Course Objectives
At the conclusion of this course you will be able to: 
* Identify states of a system 
* Partition information into states, inputs, and observations 
* Determine observability of a state 
* Identify an appropriate estimation approach for a given problem
* Combine observations in an "optimal" manner 
* Combine observations with system models to uncover latent states for a range of systems 
* Identify failure modes and weaknesses of different estimators 

### Course Prerequisites
This course has no formal prerequisites but a basic knowledge of programming, differential equations, and linear algebra is important. You should be comfortable writing MATLAB or python functions that implement simple equations. You should also be familiar with linear algebra concepts including matrix multiplication and inversion. 

A good refresher on your programming skills would be to run through [these exercises](http://shiplab.hials.org/script/ppt/MATLAB%20Practice%20-%2060%20Exercises.pdf) in the language of your choice, we'll use most of the concepts in there at some point in the course. Pay special attention to matrix operations, functions, and the difference between matrix and element multiplication. The exercises are written for MATLAB but can be completed in python as well. We will discussion as a class what language to baseline around early in the class.

### Meeting Times:
Class will meet from 4:30 to 5:50 pm Monday and Wednesday in Liberal Arts Building room 210

### Course Communication
Office Hours:\
TBD\
or by appointment

Email is the best way to contact me. I will attempt to respond within 24-48 hours, please include the course title or number in your email subject.

## Course Resources

### Required Materials
Course content will draw heavily on the following books. Readings will be assigned for each lecture, sometimes linked to multiple books if the content can be found in each. I expect you to arrive to class having completed the reading from at least one of the books.
* Optimal State Estimation by Dan Simon
* [State Estimation for Robotics by Timothy Barfoot](http://asrl.utias.utoronto.ca/~tdb/bib/barfoot_ser17.pdf)
* Probabilistic Robotics by Sebastian Thrun, Wolfram Burgard, Dieter Fox
* [Pattern Recognition and Machine Learning by Christopher Bishop](https://www.microsoft.com/en-us/research/uploads/prod/2006/01/Bishop-Pattern-Recognition-and-Machine-Learning-2006.pdf)

Copies of most of these texts are available on reserve in the library. Some of them are available (linked above) from the author's websites as pdfs. Homework will not be assigned from these texts so there is no specific need to purchase a textbook or a particular version. However, you may benefit from reading their perspectives and if you plan to continue working in this area having a reference text is very handy.

### Electronic Resources
Modern engineering practice draws heavily on electronic resources broadly available including technical papers, content from online courses, technical forums, blog posts, and wikipedia. Recognizing this, you are encourged to make careful use of these resources. They can be valuable references but their quality and notation can vary. Ultimately you will be tasked with developing solutions to novel problems in your careers so it is critical that an understanding of the theory of a solution is developed rather than simply stringing together code snippets from stackoverflow. There are no restrictions on the resources you makes use of, but resources must be clearly documented, including a way for me to access a resource, a description of what was obtained from each resource, and how it was used.

## Course Structure and Sequence
Course content will primarily be delivered through lecture. The course will have three primary sections.

### Preliminaries
In the first part of the course we will develop the theoretical underpinnings of estimation theory. This section will:
* cover notions of probability 
* develop tools for working with probability distributions
* apply these to measurements of engineering systems
* describe the states of a sytem

### Batch Estimation
We will learn how these tools can be used to determine the states of a system given a collection of data. This will include
* maximum likelihood estimation
* nonlinear extensions
* priors and their use
 
### Filtering
This section of the course will use the theoretical underpinnings to devleop the notion of a filter and derive the Kalman filter, a commonly used filtering technique. Content will include:
* refining information
* state-space representation of systems
* transforming probability distributions
* developing the notion of a filter
* deriving the Kalman filter
* Extensions of the kalman filter

## Assignments and Evaluation
Progress in this course will be evaluated through homework, exams, hands-on activities, and a final project.

### Exercises
You will be assigned regular exercise problems. These will not be scored directly. Instead you will have two opportunities for reflection and feedback. 

In the first you will be asked to discuss your approach to and progress on an exercise which is not yet complete. You will have three minutes to present and two for questions, your discussion should cover:
* what do you think the key features of the problem are
* a brief sketch of how you might solve it (don't solve! you only have three minutes)
* what parts do you think might be tricky
You will be expected to engage with other students discussion in a constructive manner. Ask them or the class questions! Gently suggest something if you think they are mistaken! If you are presenting and aren't sure about something, use this to get feedback from the class on an idea!

The second opportunity will occur after the exercise is due. You will evaluate your solution against a key and a rubric. Indicate what you got wrong and discuss why. This works best if you write on your original solution with a different color. You will turn in the corrected solution.

My perspective on these exercises are that they exist to:
* give you a low stakes opportunity to practice
* identify conceptual or practical weaknesses in your understanding
* provide feedback on your learning to you and to me

To this end, your exercises will be evaluated on how you are engaging with these objectives, rather than on your solutions themselves.

### Exams
The course will feature one exam, which will occupy a class period.

### Hands-On Activities
Hands-on activities will require you to apply course content to several robotics and automation problems. Each activity will begin with a brief introduction to the problem and you will be provided with a simulation and data handling framework that needs a state estimation solution implemented. Each activity will culminate in a class activity where the solutions you implement will interact live with a physical system of some kind. You will have the opportunity to refine your solutions as a result of the experiments. At the conclusion of each activity you will provide a data set and your solution to the estimation problem. You will have the following week to provide documentation and discussion of your solution covering:

* A mathematical model describing the theoretical basis for your solution
* Design choices made in the implementation of your estimator
* Revisions made as a result of the experiments
* Analysis of the possible failure modes of your estimator
* Analysis of the performance of the estimator

Reports should cover no more than three total pages including figures and equations but excluding references (aim for no more than ~2 pages of written content). Any resources used in designing or implementing solutions to the activity problems should be documented. 

You should also turn in commented source code. Comments should not describe what a line of code does, but rather why you are doing something. For example, this is an example of a good comment:
```
% I make a forward euler approximation in the state dynamics. This allows me to
% use the continuous-time dynamics matrix I've derived to propagate the discrete
% time dynamics. This will break down if my time step sizes get too large or if
% the dynamics are very fast.
A_step = eye(2) + A * dt;
X_ = A_step * X_ + B * u * dt;
```
While this is not an adequate comment:
```
% propagate the state vector forward
A_step = eye(2) + A * dt;
X_ = A_step * X_ + B * u * dt;
```
If you use code snippets which are not original work, the snippets should be accompanied by referenced comments identifying the source of the snippet in a way I can access (url) and a 1-2 sentence explanation of what that snippet does. For example:
```
% uniformly sample initial position on earth. I knew that sampling randomly from 
% latitude and longitude would over-sample the poles and under-sample the 
% tropics. I figured that the earth is close enough to spherical that if I 
% sampled on a sphere and normalized it to the earth's size that that would be 
% close enough, but couldn't think of how to do this sampling, I found this 
% solution on stackexchange and translated it from R code to matlab.
% https://stats.stackexchange.com/q/7988
n_samples = 1000;
z_sample = 2 * rand(n_samples, 1) - 1;
theta_sample = 2 * pi * rand(n_samples, 1) - pi;
x_sample = sin(theta) .* sqrt(1 - z.^2);
y_sample = cos(theta) .* sqrt(1 - z.^2);
R_earth = 6378137.0; % semi-major axis from https://en.wikipedia.org/wiki/World_Geodetic_System
x = x_sample * R_earth;
y = y_sample * R_earth;
z = z_sample * R_earth;
```
Note that you are still responsible for your solution being correct and working. For example -- before I put this example in I did some basic checks (plotting the output and checking the statistics against a uniform lat-lon sample to make sure they were different). 

### Project
You will also complete a self-identified project requiring application of the concepts and practice of state estimation. You are encouraged to draw the project content from your personal or professional interests. You should discuss a project topic with me and we will agree on an appropriate scope and deliverable. Projects may work with real or simulated systems but your system must:

* have at least one state which is not directly observed
* have at least one state which is dynamic
* have a nonlinearity in the dynamics and / or observations

At the conclusion of the semester you will turn in a final project report no more than 10 total pages (excluding references). Source code should be provided and follow the same documentation requirements as the activities. Your report should cover:

* Identification of inputs, states, and sensors
* Analysis of the probabilistic nature of your system
* Derivation of a system model
* Analysis of observability
* Discussion of an appropriate estimation approach
* Implementation of the estimator
* Test results
* Analysis of results
* Discussion of the limitations of the approach adopted and failure modes of the estimator

You will be provided suggested milestones. I very strongly recommend you satisfy them. This is a major undertaking and will take you several weeks to complete satisfactorily

### Grade Expectations
Rubrics for evaluation of course assignments will be constructed so that a "C" level grade indicates a satisfactory solution to the assigned problem but without demonstrating an understanding of the theoretical background for the problem and its solution. A "B" level grade will indicate both solution of the assigned problem and an understanding of its theoretical properties. "A" level grades will indicate that in addition to "C" and "B" level mastery that you understand the limitations of the solution developed.

### Assignment Weighting
Final grades will be assigned with a weighted combination of component grades according to the following breakdown

| Deliverable | Weight |
|-------|--------|
| Exercise Completion and Evaluation | 0.1 |
| Exercise Progress Discussion | 0.1 |
| Participation in Discussion | 0.05 |
| Exam | 0.15 |
| Activities | 0.4 |
| Project | 0.2 |

## Preliminary Schedule 

| Day | Due | Lecture | Relevant Text |
|-------|--------|--------|--------| 
|2025-08-25 |  | Introduction |  |
|2025-08-27 |  | Probability Distributions | Barfoot, 2.1.1; Simon, 2.1 |
|2025-09-01 |  | Labor Day |  |
|2025-09-03 | E1 | Joint, Marginal, and Independent Distributions | Barfoot, 2.1.5-2.1.6; Simon, 2.2, 2.4 |
|2025-09-08 |  | Distributions and Random Variables |  |
|2025-09-10 | E2 | Moments, Expectation and Covariance | Barfoot, 2.1.3-2.1.5
Simon, 2.2 |
|2025-09-15 |  | The Gaussian PDF, Conditioning | Barfoot, 2.2.1, 2.2.3 |
|2025-09-17 | E3 | Conditioning on Observations | Barfoot, 2.2.3 |
|2025-09-22 |  | Reserved |  |
|2025-09-24 |  | Exam |  |
|2025-09-29 |  | Linear-Gaussian Maximum Likelihood | Simon, 3.1. 3.2
Barfoot, 3.1-3.1.2 |
|2025-10-01 | E4 | Linear-Gaussian Maximum Likelihood Continued |  |
|2025-10-06 |  | Nonlinear ML, Activity 1 Introduction | Barfoot 4.3.3 |
|2025-10-08 |  | Nonlinear ML, Continued |  |
|2025-10-13 | E5 | Priors |  |
|2025-10-15 |  | Activity 1 |  |
|2025-10-20 |  | Sequential Estimation |  |
|2025-10-22 | A1 | State Space Representation, Project Intro |  |
|2025-10-27 | E6 | Transforming Distributions |  |
|2025-10-29 |  | Kalman Filter, Activity 2 Introduction |  |
|2025-11-03 |  | Kalman Filter, continued |  |
|2025-11-05 | E7 | Initialization of KF |  |
|2025-11-10 |  | Reserved |  |
|2025-11-12 |  | Activity 2 |  |
|2025-11-17 |  | Filter Consistency |  |
|2025-11-19 | A2 | Steady-state ﬁlter |  |
|2025-11-24 |  | Extended Kalman ﬁlter |  |
|2025-11-26 |  | Extended Kalman ﬁlter |  |
|2025-12-01 | E8 | EKF divergence |  |
|2025-12-03 |  | Reserved |  |


## Course Policies

### Technology Requirements
Homework, activities, and projects will require computer software programming. You will be provided with templates for the activities and some homeworks. We will decide as a class whether to use MATLAB or python for templates. Projects are a bit more open and will be discussed during the assignment. MATLAB software can be obtained through [this link](https://www.utep.edu/technologysupport/ServiceCatalog/SOFTWARE_PAGES/soft_matlab.html)

You will have to install some additional libraries to complete the activities.

If you do not have access to a laptop, you can [borrow one from from the library](https://www.utep.edu/technologysupport/TSCenter/TSC_EQ_LaptopsTablets.html)

Activity and project reports should be submitted as zip files contining a PDF report and a "software" folder through the blackboard system.

### Course Attendance Policy
There will be no formal attendance taken, but you are expected to be engaged in the homework discussions. Further, each activity will include one class period dedicated to interaction with an information system. These interactions will generate the data which will be the basis of the activity report so attendance will be required to complete the activity. If you are unable to attend class during one of the activities should contact me at least 24 hours prior to the class to make alternate arrangements, if you have an emergency pop up contact me when it is practical to do so.

### Late Work Policy
Assignments may be accepted at my discretion provided that you contact me more than 24 hours in advance and receive an extension. Absent an emergency or prior extension, work that is simply not turned in on time will not be accepted after the deadline.

### Accommodations Policy
The University is committed to providing reasonable accommodations and auxiliary services to students, staff, faculty, job applicants, applicants for admissions, and other beneficiaries of University programs, services and activities with documented disabilities in order to provide them with equal opportunities to participate in programs, services, and activities in compliance with sections 503 and 504 of the Rehabilitation Act of 1973, as amended, and the Americans with Disabilities Act (ADA) of 1990 and the Americans with Disabilities Act Amendments Act (ADAAA) of 2008. Reasonable accommodations will be made unless it is determined that doing so would cause undue hardship on the University.  Students requesting an accommodation based on a disability must register with the UTEP Center for Accommodations and Support Services (CASS).​ Contact the Center for Accommodations and Support Services at 915-747-5148, or email them at cass@utep.edu, or apply for accommodations online via the CASS portal.

### Academic Integrity
Academic dishonesty is prohibited and is considered a violation of the UTEP Handbook of Operating Procedures. It includes, but is not limited to, cheating, plagiarism, and collusion. Cheating may involve copying from or providing information to another student, possessing unauthorized materials during a test, or falsifying research data on laboratory reports. Plagiarism occurs when someone intentionally or knowingly represents the words or ideas of another as ones' own. Collusion involves collaborating with another person to commit any academically dishonest act. Any act of academic dishonesty attempted by a UTEP student is unacceptable and will not be tolerated. All suspected violations of academic integrity at The University of Texas at El Paso must be reported to the Office of Student Conduct and Conflict Resolution (OSCCR) for possible disciplinary action. To learn more, please visit HOOP: Student Conduct and Discipline.
