# Our computing systems

Our group’s main computing resources are:&#x20;

* NERSC (the LBNL supercomputing center, one of the biggest in the world) – unfortunately, due to way NERSC is funded, only some projects are eligible to run on NERSC.
* NREL Eagle – some projects that cannot use NERSC can run on the Eagle supercomputer
* Lawrencium – we have a yearly allocation on this computer that can be used for any project, but usage needs to be coordinated amongst the different projects in the group. We can also pay-per-hour if needed or even purchase nodes on Lawrencium if needed.

At any time, if you feel you are computing-limited, please contact Anubhav so he can work with you on finding solutions.

## More details on NERSC

To get started with calculations at NERSC:

1. Ask Anubhav about whether you will be running at NERSC and, if so, under what account / repository to charge.
2. Request a NERSC account through the NERSC homepage (Google “NERSC account request”).
3. Someone at NERSC will validate your account and assign you computing hours
4. At this point, you should be able to log in, check CPU-hour balances, etc. at [https://iris.nersc.gov ](https://iris.nersc.gov)and [https://my.nersc.gov](https://my.nersc.gov).
5. In order to log in and run jobs on the various machines at NERSC, review the NERSC documentation.
6.  In order to load and submit scripts for various codes (VASP, ABINIT, Quantum Espresso), NERSC has lots of information to help. Try Google, e.g. “NERSC VASP”. a. Note that for commercial codes such as VASP, there is an online form that allows you to enter your VASP

    license, which NERSC will confirm and then allow you access to.&#x20;
7.  Please make a folder inside your project directory and submit all your jobs there as your home folder has only about 40GB of space. For example, for m2439 project, your work folder path should be something like the following:

    a. /global/project/projectdirs/m2439/YOUR\_NERSC\_USERNAME
8.  If you are using custom Python software in your jobs (such as atomate), it is recommended to install it in the dedicated “software” directory. This is because this folder has much faster IO for the compute nodes than the project or home directories and running Python software often requires accessing many files (rather than just a single executable such as VASP). For example, for the m2439 project, you should install compute-critical Python software in:

    a. /global/common/software/m2439/
9. You can also request a database for your project to be hosted on NERSC. Google “MongoDB on NERSC” for instructions.
10. If you are interested in hosting web sites at NERSC, visit the workshop on Spin

    [https://www.nersc.gov/users/training/events/](https://www.nersc.gov/users/training/events/)
11. Jupyter notebooks are quickly becoming an indispensable tool for doing computational science. In some cases, you might want to (or need to) harness NERSC computing power inside of a jupyter notebook. To do this, you can use NERSC’s new Jupyterhub system at https://jupyter.nersc.gov/.

## More details on Lawrencium

To use Lawrencium resources, first apply for a new account by visiting this link

[https://it.lbl.gov/resource/hpc/for-users/hpc-documentation/accounts/user-accounts/](https://it.lbl.gov/resource/hpc/for-users/hpc-documentation/accounts/user-accounts/)&#x20;

and fill out the user agreement form here

[https://sites.google.com/a/lbl.gov/high-performance-computing-services-group/useragreement](https://sites.google.com/a/lbl.gov/high-performance-computing-services-group/useragreement)

and then send an email to hpcshelp@lbl.gov to request an account - make sure the email specifically requests access to the “lr\_matminer” condo. Once your account is ready and you are able to login, you can see the group softwares that are not available on Lawrencium by default here: /global/common/software/m2439/example\_config\_cori
