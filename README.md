## Table Of Contents

* [Pre-requisites](#pre-requisites)
* [Run Your First Test](#run-your-first-test)
* [Local Testing With pytest](#testing-locally-hosted-or-privately-hosted-projects)
## Prerequisites

Before you can start performing **Python 3** automation testing using **pytest**, you would need to:

* Install the latest Python build from the [official website](https://www.python.org/downloads/). We recommend using the latest version.
* Make sure **pip** is installed in your system. You can install **pip** from [here](https://pip.pypa.io/en/stable/installation/).
* Download the latest **Selenium Client** and its **WebDriver bindings** from the [official website](https://www.selenium.dev/downloads/). Latest versions of **Selenium Client** and **WebDriver** are ideal for running your automation script on LambdaTest Selenium cloud grid.
* Install **virtualenv** which is the recommended way to run your tests. It will isolate the build from other setups you may have running and ensure that the tests run with the specified versions of the modules.

```bash
pip install virtualenv
```
### Installing Selenium Dependencies And Tutorial Repo

**Step 1:** Clone the LambdaTest’s pytest-selenium-sample repository and navigate to the code directory as shown below:
```bash
git clone https://github.com/balaji-arun/lambdatest.git
cd lambdatest
```
**Step 2:** Create a virtual environment in your project folder the environment name is arbitrary.
```bash
virtualenv venv
```
**Step 3:** Activate the environment.
```bash
source venv/bin/activate
```
**Step 4:** Install the [required packages](https://github.com/LambdaTest/pytest-selenium-sample/blob/master/requirements.txt) from the cloned project directory:
```bash
pip install -r requirements.txt
```

### Setting Up Your Authentication

Make sure you have your LambdaTest credentials with you to run test automation scripts. You can get these credentials from the [LambdaTest Automation Dashboard](https://automation.lambdatest.com/build/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample) or by your [LambdaTest Profile](https://accounts.lambdatest.com/login/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample).

**Step 5:** Set LambdaTest **Username** and **Access Key** in environment variables.

* For **Linux/macOS**:
  
  ```bash
  export LT_USERNAME="YOUR_USERNAME" 
  export LT_ACCESS_KEY="YOUR ACCESS KEY"
  ```
  * For **Windows**:
  ```bash
  set LT_USERNAME="YOUR_USERNAME" 
  set LT_ACCESS_KEY="YOUR ACCESS KEY"
  ```

## Run Your First Test

>**Test Scenario**: The [lt_sample_todo.py](https://github.com/LambdaTest/pytest-selenium-sample/blob/master/tests/lt_sample_todo.py) sample script tests a simple to-do application with basic functionalities like mark items as done, add items in a list, calculate total pending items etc.

### Configuration Of Your Test Capabilities

**Step 6:** In the python script, you need to update your test capabilities. In this code, we are passing browser, browser version, and operating system information, along with LambdaTest Selenium grid capabilities via capabilities object. 

The capabilities object in the above code are defined as:

```python
capabilities = {
        "build": "your build name",
        "name": "your test name",
        "platformName": "Windows 10"
        "browserName": "Chrome",
        "browserVersion": "latest",
}
```
You can generate capabilities for your test requirements with the help of our inbuilt [Desired Capability Generator](https://www.lambdatest.com/capabilities-generator/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample).


### Executing The Test

**Step 7:** You would need to execute the below command in your terminal/cmd.

```bash
pytest -s tests/lambda_landing_page.py
```
Your test results would be displayed on the test console (or command-line interface if you are using terminal/cmd) and on LambdaTest automation dashboard. [LambdaTest Automation Dashboard](https://automation.lambdatest.com/build/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample) will help you view all your text logs, screenshots and video recording for your entire automation tests.

## Run Your Parallel Tests Using PyTest Framework

To run parallel tests using PyTest, we would have to execute the below command in the terminal:

```bash
pytest --workers 2 -s tests/lambda_landing_page.py
```




```


