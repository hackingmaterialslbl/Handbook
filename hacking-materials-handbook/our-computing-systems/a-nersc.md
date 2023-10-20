# A: NERSC

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
10. Visit the workshop on Spin

    [https://www.nersc.gov/users/training/events/](https://www.nersc.gov/users/training/events/)
