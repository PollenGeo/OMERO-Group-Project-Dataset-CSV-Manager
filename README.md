=========================================
OMERO Group Project-Dataset CSV Manager
=========================================

Description:
------------
This script automates the creation and organization of Projects and Datasets
in OMERO based on a structured CSV file. By reading group, project, and dataset
information, it connects to the OMERO server, switches groups as needed, and
ensures that each dataset is created (if missing) and properly linked to its
corresponding project. This makes it easier to batch-import and standardize
data organization across groups.

Features:
---------
- Secure connection to an OMERO server using user credentials.
- Supports switching between OMERO groups.
- Automatically creates Projects and Datasets if they do not already exist.
- Ensures Datasets are properly linked to their Projects.
- Reads configuration from a flexible CSV file with groups, projects, and datasets.
- Provides a graphical interface for selecting the CSV file and entering credentials.
- Displays a summary of created or linked objects.

CSV File Format:
----------------
The CSV file should contain the following columns:

- `groups`  
  - Group name or group ID.
- `project`  
  - Project name or Project ID.
- `dataset`  
  - One or multiple Dataset names (comma-separated).

Example:

groups,project,dataset
1,118,Dataset_A
45,TEST2,test2,test23


Requirements:
-------------
The script requires the following Python libraries:
- `tkinter` (included in most Python distributions)
- `csv` (standard library)
- `shlex` (standard library)
- `subprocess` (standard library)
- `omero-gateway`
- `omero.model`
- `ezomero`

Installation:
-------------
Before running the script, install the required packages:

pip install omero-py
pip install ezomero

If `tkinter` is missing (common on some Linux distributions), install it manually:

sudo apt-get install python3-tk


Usage:
------
1. Run the script:
python Omeromanager.py
2. Enter the OMERO host, username, and password when prompted.
3. Select the CSV file with your group, project, and dataset definitions.
4. The script will:
- Switch to each specified group.
- Create or retrieve the projects and datasets.
- Link datasets to projects if needed.
- Display a summary of processed items.
5. A confirmation dialog will appear with the full summary.

Author:
-------
This script was developed by **Daurys De Alba**.

Contact:
--------
- Email: daurysdealbaherra@gmail.com  
- Email: DeAlbaD@si.edu  
