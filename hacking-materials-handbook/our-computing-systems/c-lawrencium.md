# C: Lawrencium

Lawrencium is somewhat different than NERSC in that we must maintain our own software environment and pre-installed binaries for common codes are not available. Thus, maintaining the software environment at Lawrencium is a group endeavour. We currently have 4 nodes which means as a group we can submit jobs that require up to 4 nodes and those jobs will have the highest priority to start running. Note that if our purchased nodes are not enough to sustain our computing needs, it is also possible to pay per CPU-hour on Lawrencium as well as to increase our purchase order to increase our nodes. Ask Anubhav if you think you need this.

The nodes on Lawrencium are not that fast (2.3 GHz) but there is large number of cores (24 per node). So, it is best for codes that parallelize. Also, make sure to do any file-based work on Lawrencium on the /scratch filesystem, which is not purged. Any operation (loading software libraries, output file writing, etc) that occurs on the /home filesystem will be extremely slow. So /home is just for archival purposes, not working purposes.

To use Lawrencium resources, first apply for a new account by visiting this link

[https://it.lbl.gov/resource/hpc/for-users/hpc-documentation/accounts/user-accounts/](https://it.lbl.gov/resource/hpc/for-users/hpc-documentation/accounts/user-accounts/)&#x20;

and fill out the user agreement form here

[https://sites.google.com/a/lbl.gov/high-performance-computing-services-group/useragreement](https://sites.google.com/a/lbl.gov/high-performance-computing-services-group/useragreement)

and then send an email to hpcshelp@lbl.gov to request an account - make sure the email specifically requests access to the “lr\_matminer” condo. Once your account is ready and you are able to login, you can see the group softwares that are not available on Lawrencium by default here: /global/common/software/m2439/example\_config\_cori
