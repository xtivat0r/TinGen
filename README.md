# TinGen
Script that will allow you to easily generate an index file (with encryption if needed) for use with Tinfoil. 

This project is a based on [this project](https://github.com/BigBrainAFK/tinfoil_gdrive_generator/) by [BigBrainAFK](https://github.com/BigBrainAFK/).  
  
**NOTE: The token generated by this script can also be used with Tinfoil.**  

All tinfoil indexes are generated with the following format: [Tinfoil-New-Index-Info.md](https://gist.github.com/eXhumer/97cf2258db7fd1074dc1c9d06409cd4b)

## Requirements
- Python 3
- Modules from `requirements.txt` found in the root of project directory.
- `credentials.json` (or any file name if using `--credentials` flag to pass custom location for the required credential file). It can be obtained from [here](https://developers.google.com/drive/api/v3/quickstart/python) by clicking the `Enable Drive API` button in there while being signed in with the user account you want to generate credentials for or from Google's Developer Console.
- Google Drive Folder IDs to scan and index.

Execute the following command in a terminal to install all the required modules.  
```
pip3 install -r requirements.txt
```

## Usage
```
usage: TinGen.py [-h] [--credentials CREDENTIALS_FILE_NAME] [--token TOKEN_FILE_PATH] [--headless]
                 [--index-file INDEX_FILE_PATH] [--share-files] [--no-recursion] [--add-nsw-files-without-title-id]
                 [--add-non-nsw-files] [--success SUCCESS_MESSAGE] [--encrypt] [--public-key PUBLIC_KEY_FILE_PATH]
                 [--vm-file VM_FILE] [--upload-to-folder-id UPLOAD_FOLDER_ID] [--upload-to-my-drive]
                 [--new-upload-id] [--share-uploaded-index] [--zstandard | --zlib | --no-compress]
                 [FOLDER_ID_TO_SCAN [FOLDER_ID_TO_SCAN ...]]

Script that will allow you to generate an index file with Google Drive file links for use with Tinfoil

positional arguments:
  FOLDER_ID_TO_SCAN     Folder IDs of Google Drive folders to scan

optional arguments:
  -h, --help            show this help message and exit
  --credentials CREDENTIALS_FILE_NAME
                        File path to Google Credentials file
  --token TOKEN_FILE_PATH
                        File path of a Google Token file
  --headless            Allows to perform Google Token Authentication in headless environment
  --index-file INDEX_FILE_PATH
                        File path for index file
  --share-files         Share files all files inside the index file
  --no-recursion        Scans for files only in top directory for each folder ID entered
  --add-nsw-files-without-title-id
                        Adds files without title ID
  --add-non-nsw-files   Adds files without valid NSW ROM extension(NSP/NSZ/XCI/XCZ) to index
  --success SUCCESS_MESSAGE
                        Adds a success message to index file to show if index is successfully read by tinfoil
  --encrypt             Encrypts the resulting index file
  --public-key PUBLIC_KEY_FILE_PATH
                        File Path for Public Key to encrypt with
  --vm-file VM_FILE     File Path for VM File
  --upload-to-folder-id UPLOAD_FOLDER_ID
                        Upload resulting index to folder id supplied
  --upload-to-my-drive  Upload resulting index to My Drive
  --new-upload-id       Uploads the newly generated index file with a new file ID instead of replacing old one
  --share-uploaded-index
                        Shares the index file that is uploaded to Google Drive
  --zstandard           Compresses index with Zstandard compression method
  --zlib                Compresses index with Zlib compression method
  --no-compress         Flag to not compress index

```

## Credits
* [BigBrainAFK](https://github.com/BigBrainAFK/) for inital crypto script for index encryption.
* [blawar](https://github.com/blawar/) for tinfoil and for early access to details about new index format and supported compression methods and also for helping me with my dumb questions. 
