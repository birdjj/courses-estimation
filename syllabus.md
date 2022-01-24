---
layout: page
title: Syllabus 
permalink: /syllabus/
---
* toc 
{:toc}

## Course Information
Title: Special Topics -- State Estimation for Robotics and Autonomous Systems\
Number: MECH 4395 / 5395\
CRN: 22990 / 26376\
Term: Spring 2022\
Instructor: John Bird\
Office: Engineering Building A-115\
Instructor email: jjbird@utep.edu\
Instructor phone: 915.747.8406

This course is cross-listed as both an undergraduate (4395 / 22990) and graduate (5395 / 26376) course. Please ensure that you are enrolled in the correct section.

### Course Description
State estimation is concerned with determining the internal states of a system by combining sensor measurements. Estimation is fundamental to many mobile robotics, aerospace, and process control systems. In this course we will study basic probability and system theory underlying estimation, techniques to determine if a state can be estimated from available observations, and state estimation algorithms for linear and nonlinear systems.

### Course Objectives
At the conclusion of this course you will be able to: 
* Identify states of a system 
* Write a probabilistic graphical model for a system 
* Partition information into states, inputs, and observations 
* Determine observability of a state 
* Identify an appropriate estimation approach for a given problem
* Combine observations in an "optimal" manner 
* Combine observations with system models to uncover latent states for a range of systems 
* Identify failure modes and weaknesses of different estimators 

### Course Prerequisites
This course has no formal prerequisites but a basic knowledge of MATLAB programming and linear algebra is important. You should be comfortable writing MATLAB functions that implement simple equations. You should also be familiar with linear algebra concepts including matrix multiplication, inversion, and rank.

### Meeting Times:
Class will meet from 1:30 to 2:50 pm Monday and Wednesday in room 208 in the Liberal Arts building.

### Course Communication
Office Hours:\
Mondays in-person 10:30--12:00\
Wednesdays virtually 15:00--16:30\
or by appointment

Email is the best way to contact me. I will attempt to respond within 24-48 hours, please include the course number in your email subject.

## Course Resources

### Required Materials
No textbooks are required for this class. The content will draw heavily on:
* Optimal State Estimation by Dan Simon
* [State Estimation for Robotics by Timothy Barfoot](http://asrl.utias.utoronto.ca/~tdb/bib/barfoot_ser17.pdf)
* Probabilistic Robotics by Sebastian Thrun, Wolfram Burgard, Dieter Fox
* [Pattern Recognition and Machine Learning by Christopher Bishop](https://www.microsoft.com/en-us/research/uploads/prod/2006/01/Bishop-Pattern-Recognition-and-Machine-Learning-2006.pdf)

Copies of most of these texts are available on reserve in the library. Some of them are available (linked above) from the author's websites as pdfs. Homework will not be assigned from these texts so there is no specific need to purchase a textbook or a particular version.

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
* develop techniques for separating states from inputs and observed from hidden information
 
### Filtering
This section of the course will use the theoretical underpinnings to devleop the notion of a filter and derive the Kalman filter, a commonly used filtering technique. Content will include:
* refining information
* state-space representation of systems
* transforming probability distributions
* developing the notion of a filter
* deriving the Kalman filter

### Advanced Topics
This section of the course will extend the previous sections to more complicated situations where states or observations are drawn from complicated probability distributions, are associted with nonlinear systems, or are extremely large in dimension. We will discuss:
* Failure modes of filters
* Extensions of the kalman filter
* non-parametric filters
* ensemble filters

## Assignments and Evaluation
Progress in this course will be evaluated through homework, exams, hands-on activities, and a final project.

### Homework
You will be assigned weekly homework problems. Homework will not be graded, however you will be asked to review and provide feedback on each other's homework. During each lecture a student will discuss a homework problem with the class. On Mondays a student will present a critique of a problem from a peer's homework. On Wednesdays a student will discuss their understanding of and progress on the latest homework. Friday morning the solutions to a homework will be provided and a new homework will be issued which will cover the following week's material. 

### Exams
The course will feature two exams, each will occupy one class period. Exams will be open to any static content (written and electronic references permissible, but no live communication). References should be cited during any development or explanation, and problems where you reference external content should have a brief statement at the end describing the information or insight gained from each reference. References should be in the following format:

(when deriving the information filter equations) [1][2]

explanation of thing, e.g. how Kalman gain varies as measurement noise goes to zero [3]

1. https://en.wikipedia.org/wiki/Woodbury_matrix_identity "Discussion"\
    I could not recall the matrix inversion lemma
2. notes from Lecture X\
    Notes that the information filter propagates the inverse of covariance
3. Barfoot. "State Estimation for Robotics." Pg 65\
    Notes that the Kalman gain weights the innovation contribution to the estimate

Reference lists can be either per problem or per exam. If only books are used as references the list can be handwritten. If electronic resources are used then an electronic document with the references should be turned in with the exam.

### Hands-On Activities
Hands-on activities will require you to apply course content to several robotics and automation problems. Each activity will begin with a brief introduction to the problem and you will be provided with a simulation and data handling framework that needs a state estimation solution implemented. Each activity will culminate in a class activity where the solutions you implement will interact live with a physical system of some kind. You will have the opportunity to refine your solutions as a result of the experiments. At the conclusion of each activity you will provide a data set and your solution to the estimation problem. You will have the following week to provide documentation and discussion of your solution covering:

* A mathematical and graphical model describing the theoretical basis for your solution
* Design choices made in the implementation of your estimator
* Revisions made as a result of the experiments
* Analysis of the possible failure modes of your estimator
* Analysis of the performance of the estimator

Reports should cover no more than three total pages including figures and equations but excluding references (aim for no more than 1.5--2 pages of written content). Any resources used in designing or implementing solutions to the activity problems should be documented. 

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
You will also complete a self-identified project requiring application of the concepts and practice of state estimation. You are encouraged to draw the project content from your research, personal, or professional interests. You should discuss a project topic with me and we will agree on an appropriate scope and deliverable. Projects may work with real or simulated systems but require:

* Construction of a probabilistic graphical model
* Identification of inputs, states, and sensors
* Derivation of a system model
* Analysis of observability
* Discussion of an appropriate estimation approach
* Implementation of the estimator
* Test results
* Analysis of results
* Discussion of the limitations of the approach adopted and failure modes of the estimator

At the conclusion of the semester you will turn in a final project report no more than 10 total pages (excluding references). Source code should be provided and follow the same documentation requirements as the activities.

### Grade Expectations
Rubrics for evaluation of course assignments will be constructed so that a "C" level grade indicates a satisfactory solution to the assigned problem but without demonstrating an understanding of the theoretical background for the problem and its solution. A "B" level grade will indicate both solution of the assigned problem and an understanding of its theoretical properties. "A" level grades will indicate that in addition to "C" and "B" level mastery that a
student understands the limitations of the solution developed.

### Assignment Weighting
Final grades will be assigned with a weighted combination of component grades according to the following breakdown

| Deliverable | Weight |
|-------|--------|
| Course Participation | |
| -- Homework Critique | 0.05 |
| -- Progress Discussion | 0.05 |
| -- Participation in Discussion | 0.05 |
| Exams | |
| -- Exam 1 | 0.1 |
| -- Exam 2 | 0.1 |
| Activities | |
| -- Activity 1 | 0.1 |
| -- Activity 2 | 0.1 |
| -- Activity 3 | 0.1 |
| -- Activity 4 | 0.1 |
| Project | 0.25 |

## Graduate Section 
Course content will be identical between graduate and undergraduate sections. Students enrolled in the graduate section will have additional problems in the exams. They will be expected to provide a greater depth of insight into analysis of exam and activity problems, and to take on a project with slightly larger scope. 

## Preliminary Schedule 

| Day | HW | Lecture | Relevant Text |
|-------|--------|--------|--------| 
| W, 2022-01-19 | | Introduction | |
| M, 2022-01-24 | | Probability Distributions | Barfoot 2.1<br> Bishop 1.2.1, 1.2.2 |
| W, 2022-01-26 | | Probabilistic Graphical Models | Bishop 8.1--8.3 |
| M, 2022-01-31 | 1 | Expectation and Covariance |
| W, 2022-02-02 | | Combining Measurements | 
| M, 2022-02-07 | 2 | Linear Least Squares |
| W, 2022-02-09 | | Exam 1 |
| M, 2022-02-14 | 3 | Nonlinear Least Squares, Activity 1 Introduction |
| W, 2022-02-16 | | Priors |
| M, 2022-02-21 | 4 | Sequential Estimation |
| W, 2022-02-23 | | State Space Representation |
| M, 2022-02-28 | 5 | [Activity 1]({{ site.baseurl }}{% link _pages/activities/1.md %}) |
| W, 2022-03-02 | | Transforming Distributions |
| M, 2022-03-07 | 6 | Observability |
| W, 2022-03-09 | | Kalman Filter |
| Spring Break | | |
| M, 2022-03-21 | 7 | Review, Activity 2 Introduction |
| W, 2022-03-23 | | Exam 2 |
| M, 2022-03-28 | 8 | Consistency and Initialization of KF, Parameter Estimation |
| W, 2022-03-30 | | [Activity 2]({{ site.baseurl }}{% link _pages/activities/2.md %}) (last day of class before drop day) |
| M, 2022-04-04 | 9 | Non-gaussian noise, Steady-state filter, information filter |
| W, 2022-04-06 | | Extended Kalman filter, Activity 3 introduction, project introduction |
| M, 2022-04-11 | 10 | Unscented Kalman filter |
| W, 2022-04-13 | | [Activity 3]({{ site.baseurl }}{% link _pages/activities/3.md %}) |
| M, 2022-04-18 | 11 | Particle filter, Activity 4 introduction, project defined |
| W, 2022-04-20 | | Importance sampling, weighting |
| M, 2022-04-25 | 12 | Ensemble Kalman filter |
| W, 2022-04-27 | | [Activity 4]({{ site.baseurl }}{% link _pages/activities/4.md %}) |
| M, 2022-05-02 | 13 | Gaussian process regression, density estimation |
| W, 2022-05-04 | | reserved |


## Course Policies

### Technology Requirements
Homework, activities, and projects may require computer software programming. You will be provided with MATLAB / Simulink templates for the activities. MATLAB / Simulink software can be obtained through the following link:
https://www.utep.edu/technologysupport/ServiceCatalog/SOFTWARE_PAGES/soft_matlab.html

Activity and project reports should be submitted as zip files contining a PDF report and a "software" folder through the blackboard system.

### Course Attendance Policy
There will be no formal attendance taken, but you are expected to be engaged in the homework discussions. Further, each activity will include one class period dedicated to interaction with an information system. These interactions will generate the data which will be the basis of the activity report so attendance will be required to complete the activity. If you are unable to attend class during one of the activities should contact me at least 24 hours prior to the class to make alternate arrangements, if you have an emergency pop up contact me when it is practical to do so.

### Late Work Policy
Assignments may be accepted at my discretion provided that you contact me more than 24 hours in advance and receive an extension. Absent an emergency or prior extension, work that is simply not turned in on time will not be accepted after the deadline.

### Accommodations Policy
The University is committed to providing reasonable accommodations and auxiliary services to students, staff, faculty, job applicants, applicants for admissions, and other beneficiaries of University programs, services and activities with documented disabilities in order to provide them with equal opportunities to participate in programs, services, and activities in compliance with sections 503 and 504 of the Rehabilitation Act of 1973, as amended, and the Americans with Disabilities Act (ADA) of 1990 and the Americans with Disabilities Act Amendments Act (ADAAA) of 2008. Reasonable accommodations will be made unless it is determined that doing so would cause undue hardship on the University.  Students requesting an accommodation based on a disability must register with the UTEP Center for Accommodations and Support Services (CASS).​ Contact the Center for Accommodations and Support Services at 915-747-5148, or email them at cass@utep.edu, or apply for accommodations online via the CASS portal.

### COVID 19 Precautions
You are expected to adhere to university guidance on COVID 19 precautions available at:
https://www.utep.edu/resuming-campus-operations/
Guidance and policy with respect to COVID may change throughout the semester.

If you have tested positive for COVID 19 or have reason to suspect you may have COVID 19 (e.g. because of symptoms or close contact with an individual who has COVID 19) please stay home. Contact me and we will arrange appropriate accomodations. 

Students who are considered high risk according to CDC guidelines and/or those who live with individuals who are considered high risk may contact Center for Accommodations and Support Services (CASS) to discuss temporary accommodations for on-campus courses and activities.

### Academic Integrity
Academic dishonesty is prohibited and is considered a violation of the UTEP Handbook of Operating Procedures. It includes, but is not limited to, cheating, plagiarism, and collusion. Cheating may involve copying from or providing information to another student, possessing unauthorized materials during a test, or falsifying research data on laboratory reports. Plagiarism occurs when someone intentionally or knowingly represents the words or ideas of another as ones' own. Collusion involves collaborating with another person to commit any academically dishonest act. Any act of academic dishonesty attempted by a UTEP student is unacceptable and will not be tolerated. All suspected violations of academic integrity at The University of Texas at El Paso must be reported to the Office of Student Conduct and Conflict Resolution (OSCCR) for possible disciplinary action. To learn more, please visit HOOP: Student Conduct and Discipline.
