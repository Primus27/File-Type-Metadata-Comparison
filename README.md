![](readme_files/banner.png)

# Exif Metadata Comparison

## Features
 - Search all files in a specified directory (absolute/relative) 
    - Compares their file extensions (as seen in explorer) to the file extension of that file type
    - Reports on whether they match
 - Logging functionality
    - Partial: Only include errors
    - Full: Include everything

![](readme_files/demo.gif)
> Application demo (fake credentials used)

## Requirements and Installation
 - [Python 3.6+](https://www.python.org/)
 - Unix (tested)
 - Install all dependencies from the requirements.txt file. `pip3 install -r requirements.txt`

## Arguments
#### Required arguments:
  - `-sP SCAN_PATH` || `--scanPath SCAN_PATH`
    - Scan path (absolute or relative)

#### Optional arguments:
  - `-l` || `--log`
    - Enable logging of errors to "ExtExif.log"
    - Default: Disabled


  - `-la` || `--logAll`
    - Enable logging of successful results and errors to "ExtExif.log"
    - Note: Only logs whether a search was successful or not. It does not include the comparison results (though it does include the results from exiftool).
    - Default: Disabled
  
  
  - `-o` || `--toOutput`
    - Disable ASCII escape codes that would be output if the file was redirected.
    - Note: This removes text colouring in the terminal during a scan.
    - Default: Disabled (Therefore shows coloured text in terminal)

  - `--version`
    - Display program version

## Usage
 - Run `ExtExif.py` in terminal with arguments (see above)

### Starter commands
 - Run scan
    - `python3 ExtExif.py -sP SCAN_PATH`
 - Run scan w/ error log
    - `python3 ExtExif.py -sP SCAN_PATH -l`
 - Run scan and output results to a file
    - `python3 ExtExif.py -sP SCAN_PATH -o >> RESULTS_FILE`

## Changelog
#### Version 1.0 - Initial release
 - File and folder scanner for file type extension match
    - Can be relative path or absolute path
    - Returns results ready for output (using flag)
 - Output errors and/or successful results to a log file
 
#### Version 1.1 - Bug fixes
 - Fixed general bugs
 - Fixed a bug that prevented paths with spaces to be properly scanned
 
## TO DO
 - Refactor logging blocks to make maintenance easier. 