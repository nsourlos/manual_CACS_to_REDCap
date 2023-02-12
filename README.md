# Import Manual CACS measurements performed in Syngo.via to REDCap automatically

![Alt text](./manual-cacs-to-redcap.svg)

[![forthebadge](https://forthebadge.com/images/badges/made-with-python.svg)](https://www.python.org/)
[![forthebadge](https://forthebadge.com/images/badges/uses-badges.svg)](https://forthebadge.com)

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-no-red.svg)]( https://github.com/nsourlos/manual_CACS_to_REDCap)


> This tool can be used automatically import manual Calcium score measurements performed in Syngo.via (Siemens software) to REDCap. Code is adapted according to the available attributes in REDCap (named by us). 


## Documentation (by *Chat GPT*)

The documentation below was created by using the prompt 
> Write documentation for the following code

**Introduction**

The purpose of this code is to extract information from SR DICOM files and create a DataFrame that can be used to populate a REDCap database. The code uses the libraries Numpy, Pandas, OS, PyDICOM and Collections.

**Initialization**

The first section of the code imports the necessary libraries and sets some parameters required for the code to execute properly. The path to the folder containing the SR DICOM files and the path to the folder where the txt files should be saved are both set.

Then, the code checks if the folder to save the txt files exists and if it does not, creates the folder.

After that, the code creates a list of files in the folder containing the SR DICOM files and checks if there are multiple files for the same participant. This is to ensure that there are no errors in the code execution.

**Function Definition**

The code then defines a function "recurse" that takes two arguments, the DICOM file and the path to the txt file to save information. The function loops over the attributes in the DICOM file and extracts specific attributes of interest. If an attribute is a 'Content Sequence', the function is called again to keep looping over the nested attributes. If an attribute is a specific string, it is written to the txt file. If it is a numeric value inside the previous attribute, it is written to the txt file along with its accompanying attribute.

**Information Extraction**

The code then extracts the information from the SR DICOM files using the function "recurse". The function is called for each SR file in the folder and the information is appended to the txt file for that participant.

**DataFrame Creation**

The information from the txt files is then added to a DataFrame with the specified columns. The columns are the attributes to be added to the REDCap database.


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

 
## License
[MIT License](LICENSE)
