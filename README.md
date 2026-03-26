# PG_Notebook
The Photogrammetry Notebook uses PyExifTool to process drone photos and PyODM generate a point cloud.
PyExifTool: https://pypi.org/project/PyExifTool/
PyODM: https://www.opendronemap.org/pyodm/

#--- Notes ---
This is a project I made as part of my geophysics class at UBC, EOSC 556.
I am a beginner in both python and photogrammetry, so this is a learning process for me. I used Gemini to help
me generate some code and do some debugging, though it was a pretty hands on process.

The goal of the notebook is to outline and simplify some of the pre-processing you'd do in photogrammetry.
There are lots of useful diagnostics you can run based on your metadata, and many of the features in
the notebook are built to check the quality of your data. This notebook uses PyExifTool to batch import
the metadata into a Dataframe for analysis and visualization. In theory, you could run this notebook in
the field immediately after doing your survey, so you can assess the completeness and quality of your survey.

Once you're happy with your photos, you can scroll to the bottom of the notebook and run the photogrammetry
algorithm, which uses PyODM to generate a 3D point cloud from your images. Once this is done, you can import them
to the software of your choosing to make a model.

#--- File Structure ---
Generally the notebook is built to expect a file structure like this:
  project/
  ├── README.md
  ├── PG_Notebook.ipynb
  └── PG_inputs/
  └── PG_outputs/
  ├── src/
  │   ├── PG_functions.py
  └── exiftool-13.XX_64/
  │   ├── exiftool.exe
  │   ├── exiftool_files/
  │   ├── README.txt
  └── ipynb_checkpoints/
  └── Sample_Inputs/

PG_Notebook.ipynb is the actual notebook you run, where all the magic happens.
PG_inputs is the subfolder you should place your photos in, the default directory the notebook loads photos from.
PG_outputs is the default output directory for any of the plotters if called while SaveImg = True, also where PyODM's point cloud will go.
Exiftool-13.XX_64 is the folder with all the ExifTool files straight from the website. I used version 13.54 in this notebook.
ipynb_checkpoints is the subfolder jupyter notebooks makes automatically, and stores saves in.
Sample_Inputs contains some photos from a survey I did, to provide something for people to tinker with.
