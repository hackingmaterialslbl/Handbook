# Setting up a new Macbook

### Upgrade your OS&#x20;

If your computer is not using the latest OS, you should upgrade to the latest OS first.

### Installing Python development environment&#x20;

The best way to manage Python installations these days is a “conda env”. This will allow you to manage different Python “environments”, where each environment is a set of libraries that you have installed. For example, you can have one environment that uses Python 2.7 and has certain library versions installed, and another environment that uses Python 3.5 and has other libraries installed. Another advantage of conda environments is that you can apply the same procedure on NERSC and other computing centers that support conda.&#x20;

How to do this:

* Follow the online instructions on installing a conda environment and see modifications below:&#x20;
  * [http://conda.pydata.org/docs/using/index.html](http://conda.pydata.org/docs/using/index.html)&#x20;
  * (probably) prefer to install the “miniconda” version rather than anaconda
  * Install “miniconda 3”. We work in Python 3.8+ these days.&#x20;
  * When creating environments, use a command like this (note that this also installs recommended libraries): \
    `conda create --name py3 python=3 numpy matplotlib seaborn plotly pandas flask pymongo scipy sympy scikit-learn jupyter`
  * If you want a reference guide to conda commands, try: [http://conda.pydata.org/docs/using/cheatsheet.html](http://conda.pydata.org/docs/using/cheatsheet.html)

### Install high-throughput computation environment&#x20;

Our group has a set of base codebases used for performing high-throughput calculations. Note that if your project does not involve high-throughput calculation, you may need only one or two of these libraries installed – contact Anubhav if you are unsure.

* Install the following packages using a combination of `git clone >>REPO_NAME<<` and `python setup.py develop`. Start with:&#x20;
  * `git clone https://www.github.com/materialsproject/fireworks`
    * You might need to generate an ssh key for the git clone command to work:&#x20;
      * ssh-keygen -t rsa -b 4096&#x20;
      * no password is probably OK unless you are security conscious
      * add your SSH key to your Github profile
  * Then: \
    `cd fireworks` \
    `while read requirement; do conda install --yes $requirement; done < requirements.txt && python setup.py develop python setup.py develop`&#x20;
    * note that the middle line is not technically necessary, but will install requirements with anaconda which might be better than pip
  * Repeat the process above but replace `fireworks` with: &#x20;
    * `pymatgen`&#x20;
      * this one might be tricky, because you need a modern C compiler. You can try installing gcc-8 with homebrew, then setting the following environment variables:&#x20;
        * `export CC=/usr/local/bin/gcc-8`&#x20;
          * `export LDFLAGS="-L/usr/local/opt/ lapack/lib"`
          * `export CPPFLAGS="-I/usr/local/opt /lapack/include"`
    * `pymatgen-db`
    * `custodian`
    * `atomate` (note: this is on the hackingmaterials github site)
    * `matminer` (note: this is on the hackingmaterials github site)
  * If you want, you can automatically source activate your environment in your .bash\_profile file. This will automatically load your environment when you open a Terminal. Otherwise, you will start off in your default Mac Python and will likely cause you a lot of confusion

### Configure IDE&#x20;

An IDE allows you to be a much more productive coder. It is like a text editor but contains many useful keyboard shortcuts, code-completion tools, refactoring tools, and debugging/profiling tools to help you be more productive. It can also automatically reformat your code to trim line lengths and add proper whitespace to be in-line with recommended Python formatting guidelines.

Anubhav uses Cursor, and some group members also use VSCode. Get it touch with Anubhav to know which IDE is best for you!&#x20;

### Other things to do&#x20;

* Set up your Time Machine backup (make sure you have purchased or received an external hard disk). Just plug your backup drive into your monitor so when you connect to your monitor, you also back up. For detailed instructions, see:\
  [https://support.apple.com/en-us/HT204412](https://support.apple.com/en-us/HT204412). If there are (for some reason) errors in backing up, fix that issue immediately. The lab also has an online backup program which is another safeguard against lost data: [https://bit.ly/2PVPHfM.](https://bit.ly/2PVPHfM.) There are zero excuses for not doing this.

### Contributing code to software libraries

If you are unfamiliar with how to contribute back to the various software libraries we develop through Github, refer to the procedure described here:&#x20;

[http://bit.ly/2AYeT0j](http://bit.ly/2AYeT0j)

