# How to install HEASoft and SAS
After spending many weeks trying to install both HEASoft and SAS, here is the complete, comprehensive tutorial on how to do so:

1) Install Anaconda (Optional)
   - I prefer this because then it’s easy to install CIAO for Chandra Data Analysis

2) Install HEASoft:
   - Follow this tutorial: https://youtu.be/3-gobnSEuDo
     
   - Add the alias as shown at the end of the tutorial to .bashrc on Linux or ~/.bash_profile on Mac for easy initialization
     
   - On Mac, open ~/.zshrc, and add source ~/.bash_profile, so that whenever you open terminal, ~/.bash_profile is run automatically

3) Install SAS:
   - Install prerequisites: https://www.cosmos.esa.int/web/xmm-newton/sas-requirements
     
   - Download SAS from here: https://www.cosmos.esa.int/web/xmm-newton/sas-download
     
   - Install using these instructions: https://www.cosmos.esa.int/web/xmm-newton/sas-installation
     
   - Download all CCFs from here: https://www.cosmos.esa.int/web/xmm-newton/current-calibration-files
     - Before running, make sure the terminal is in the directory where you want to store your CCFs
     - I’d recommend using the RSYNC method with the whole repository, not just the Valid CCF Set
  
       
   - After this, add the following to .bashrc on Linus or ~/.bash_profile on Mac:
     - export SAS_PERL=absolute path to perlbrew installation
     - export PERL=/absolute/path/to/perlbrew/installation
     - export SAS_DIR=/absolute/path/to/SAS/installation (ending in xmmsas_20230412_1735 or something similar)
     - export SAS_CCFPATH=/absolute/path/to/CCF/folder
     - export PATH=“path entered for SAS_DIRbin:$PATH"
     - export PATH=“path entered for SAS_DIR/lib/python/:$PATH"
       
   - Add an alias for easy initialization of SAS by entering “SAS” in terminal:
     - To .bashrc on Linux or ~/.bash_profile on Mac, add “alias SAS="source $SAS_DIR/setsas.sh"
   
4) Add these to ~/.zshrc on Mac or .bashrc on Linux:
     - export PATH=“absolute path to DS9 Installation:$PATH"
     - export PATH=“path entered for SAS_DIR/bin:$PATH"
     - export PATH=“path entered for SAS_DIR/lib/python/:$PATH"
     - export PYTHONPATH=“path entered for SAS_DIR/lib/python/:$PYTHONPATH"

5) Your Installation is now complete. Remember, when working with these, you must FIRST initialize HEASoft by entering “heainit” in terminal, and then initialize SAS by entering “SAS” in terminal, as SAS requires some parts of HEASoft to work properly

6) Enjoy your X-Ray processing!
