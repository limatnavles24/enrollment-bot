# Enrollment Bot

A scripting tool to automatically enroll on UCSD WebReg.

_Note: These instructions are for Python 3, for Python 2, check [here](https://github.com/cpacker/enrollment-bot/tree/python2)_

## Requirements and Dependencies
- Python 3.x (get it [here](https://www.python.org/downloads/))
- Libraries `mechanize` and `cookielib`
- Mechanize has not been officially updated for Python 3

#### If you have root access to your machine:
- Install `cookiejar` with:
```
pip3 install cookiejar
```
- You may have to use `sudo pip install`
- Mechanize has not been officially updated for Python 3, so install [adevore's working fork](https://github.com/adevore/mechanize/tree/python3) locally as shown below:

#### If you do not have root access, or if you'd rather supply the dependencies locally:
##### Mechanize:
- After installing (see below), go to the [mechanize](https://github.com/adevore/mechanize/tree/python3) repository page and select `Download as ZIP`
- Move the unzipped `mechanize-python3` folder you just downloaded inside the project directory (`enrollment-bot/`)
- Navigate to the project directory and rename the `mechanize-python3` folder to `mechanize`
- Create an empty `__init__.py` file inside the `mechanize` folder (eg `touch mechanize/__init__.py`)

##### Cookiejar:
- Download the cookiejar.py file [here](https://hg.python.org/cpython/raw-file/7cc7c794d1cb/Lib/http/cookiejar.py) and move it to the project directory

## Usage and Installation
1. Download or clone the project
2. Navigate to the project directory
3. Modify `PID`, `PASS` and `SECTION_IDS` in `settings.py` to be your PID, password and a list of valid section IDs from WebReg
```python
# Authentication Settings
PID = 'A12345678' # change this to your PID
PASS = 'ilovepugs5' # change this to your SSO password

# Enrollment Options
SECTION_IDS = ['843721','939283','422304'] # change these to the section IDs you want to add
```
4. `chmod +x enroll` to make the script executable
5. `./enroll` to launch the script

A copy of the terminal output will be saved to `log.log` in the project directory


## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## License

Distributed under the MIT license.

## Disclaimer
- For educational purposes only: I do not condone the use of this script on actual university services
- *Use at your own risk!*
- Instructions on how to run script using `at`
- Built-in SMTP mailer to send status update on completion / failure
