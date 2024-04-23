<p align="center">
  <img src='/OTHER/LOGO.PNG' height='300'>
</p>

***
    NAME:           General-Segmentation   
    MODIFIED:       22 April 2024  
    VERSION:        0.1.0  
    LICENSE:        GNU General Public License v3.0  
    DESCRIPTION:    Convolutional Neural Network (CNN) for general segmentation of images  
    FUNDING:        Development currently has no funding to declare
	
    AUTHOR(S):      NAME                               AFFILIATION                               ROLE
                    David Helminiak                    EECE, Marquette University                Consultant, Programmer
                    Nathaniel Helminiak                CME,  United States Military Academy      Advisor, Data Preparer
***

# PROGRAM FILE STRUCTURE

    ------->ROOT_DIR
        |------->README.md
        |------->CHANGELOG.md
        |------->GeneralSegmentation.ipynb
        |------->DATA
                |------->TRAIN
                    |------->INPUTS
                    |------->LABELS
                |------->TEST
                    |------->INPUTS
                    |------->LABELS
        |------->OTHER
                    |------->LOGO.PNG
                    |------->SOCIAL.PNG
        |------->RESULTS
                |------->TRAIN
                    |------->trainingHistory.csv
                    |------->trainingTime.txt
                    |------->Model
                    |------->Progression
                |------->TEST
                    |------->dataPrintout.csv
                    |------->Predictions
                    |------->Summary
					

# INSTALLATION

The package versions do not necessarily need to match with those listed. However, should the program produce unexpected errors, installing a specific version of a package might be able to resolve the issue. 

As more functionality is continually being added, minimum hardware specifications cannot be exactly ascertained, however validation of functionality is performed on systems containing 64+ GB DDR3/4/5 RAM, 32+ CPU threads at 3.0+ GHz, 1080Ti/2080Ti+/4090 GPUs, and 1TB+ SSD storage. 

**Windows - Software**  

	Python             3.11.8
	pip                24.0
	opencv-python      4.9.0.80
	scikit-learn       1.4.1.post1
	torch              2.2.2+cu121
	torchaudio         2.2.2+cu121
	torchvision        0.17.2+cu121
	tqdm               4.66.2

**Ubuntu 22.04 - Alternate/Additional Software**
	
	Python             3.10.12
	pip                22.0.2

**GPU/CUDA Acceleration:** Highly recommended. Note that there shouldn't be a need to manually install the CUDA toolkit, or cudnn as pytorch installation using pip should come include the neccessary files.

## Windows Pre-Installation

If not already setup, install Python 3.11.8 (newer versions have not been tested for Windows) selecting the options to install for all users, and addding python.exe to PATH.

Open a command prompt (Not as an administrator!) and run the following: 

	$ python -m pip install --upgrade pip
	$ pip3 install opencv-python

## Windows Subsystem for Linux (WSL) Pre-Installation

Open "Turn Windows Features On and Off", and enable "Windows Subsystem For Linux" if it is not already. Then open PowerShell and enter:

	$ wsl.exe --install
	$ wsl.exe --update
	
Open the Microsoft Store application and search for "Ubuntu", installing the version of your choice (22.04 or newer is recommended), and completing the setup as instructed. Then open an Ubuntu terminal window and perform the following operations: 

	$ sudo apt-get update -y 
	$ sudo apt-get upgrade -y 
	$ sudo apt-get autoremove -y 
	$ sudo apt-get install -y libgl1-mesa-dev python3-pip wget git
	
## Native Ubuntu Pre-Installation

Open a terminal window and perform the following operations:
    
	$ sudo apt-get update -y 
	$ sudo apt-get upgrade -y 
	$ sudo apt-get autoremove -y 
	$ sudo apt-get install -y python3-pip wget git
    
## Main Installation

Open a terminal or command prompt and run the following:
    
	$ pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
	$ pip3 install datetime glob2 pandas pillow matplotlib natsort notebook==6.5.6 numpy tqdm scikit-learn py7zr multivolumefile opencv-python ipywidgets

## Example Dataset

An example public dataset that can be easily obtained to try this program (ExONE Stainless Steel 316L Grains 500X, by Peter Warren et al.) may be obtained through: https://www.kaggle.com/datasets/peterwarren/exone-stainless-steel-316l-grains-500x/download?datasetVersionNumber=3  

Dataset reference(s): https://arxiv.org/pdf/2307.05911.pdf  https://www.youtube.com/watch?v=60zy93X30yE  

Splitting the data into **DATA/** **TRAIN**, or **TEST** (as may be desired) copy the contents of **Grains** to **INPUTS** and **Segmented** to **LABELS** (removing the seg suffix, so the filenames match between INPUTS and LABELS)  
