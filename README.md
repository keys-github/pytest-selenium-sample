# Run Selenium Tests With pytest — TestMu AI (Formerly LambdaTest)

![171934563-4806efd2-1154-494c-a01d-1def95657383 (1)](https://user-images.githubusercontent.com/70570645/172273386-fa9606ac-3e63-4b2e-8978-3142add3e038.png)

<p align="center">
  <a href="https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/certifications/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/@TestMuAI" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

*Learn how to run your Python automation testing scripts using pytest on the TestMu AI platform*

[<img height="58" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register)


## Table Of Contents

* [Pre-requisites](#pre-requisites)
* [Run Your First Test](#run-your-first-test)
* [Local Testing With pytest](#testing-locally-hosted-or-privately-hosted-projects)
## Prerequisites

Before you can start performing **Python 3** automation testing using **pytest**, you would need to:

* Install the latest Python build from the [official website](https://www.python.org/downloads/). We recommend using the latest version.
* Make sure **pip** is installed in your system. You can install **pip** from [here](https://pip.pypa.io/en/stable/installation/).
* Download the latest **Selenium Client** and its **WebDriver bindings** from the [official website](https://www.selenium.dev/downloads/). Latest versions of **Selenium Client** and **WebDriver** are ideal for running your automation script on TestMu AI Selenium cloud grid.
* Install **virtualenv** which is the recommended way to run your tests. It will isolate the build from other setups you may have running and ensure that the tests run with the specified versions of the modules.

```bash
pip install virtualenv
```
### Installing Selenium Dependencies And Tutorial Repo

**Step 1:** Clone the TestMu AI’s pytest-selenium-sample repository and navigate to the code directory as shown below:
```bash
git clone https://github.com/LambdaTest/pytest-selenium-sample
cd pytest-selenium-sample
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

Make sure you have your TestMu AI credentials with you to run test automation scripts. You can get these credentials from the [TestMu AI Automation Dashboard](https://automation.lambdatest.com/build/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample) or by your [TestMu AI Profile](https://accounts.lambdatest.com/login/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample).

**Step 5:** Set TestMu AI **Username** and **Access Key** in environment variables.

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

**Step 6:** In the python script, you need to update your test capabilities. In this code, we are passing browser, browser version, and operating system information, along with TestMu AI Selenium grid capabilities via capabilities object. 

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
You can generate capabilities for your test requirements with the help of our inbuilt [Desired Capability Generator](https://www.testmuai.com/capabilities-generator/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample).


### Executing The Test

**Step 7:** You would need to execute the below command in your terminal/cmd.

```bash
pytest -s tests/lt_sample_todo.py
```
Your test results would be displayed on the test console (or command-line interface if you are using terminal/cmd) and on TestMu AI automation dashboard. [TestMu AI Automation Dashboard](https://automation.lambdatest.com/build/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample) will help you view all your text logs, screenshots and video recording for your entire automation tests.

## Run Your Parallel Tests Using PyTest Framework

To run parallel tests using PyTest, we would have to execute the below command in the terminal:

```bash
pytest --workers 2 -s tests/lt_sample_todo.py
```

## Testing Locally Hosted Or Privately Hosted Projects

You can test your locally hosted or privately hosted projects with TestMu AI Selenium grid using TestMu AI Tunnel. All you would have to do is set up an SSH tunnel using tunnel and pass toggle `tunnel = True` via desired capabilities. TestMu AI Tunnel establishes a secure SSH protocol based tunnel that allows you in testing your locally hosted or privately hosted pages, even before they are live.

Refer our [TestMu AI Tunnel documentation](https://www.testmuai.com/support/docs/testing-locally-hosted-pages/) for more information.

Here’s how you can establish TestMu AI Tunnel.

Download the binary file of:
* [TestMu AI Tunnel for Windows](https://downloads.lambdatest.com/tunnel/v3/windows/64bit/LT_Windows.zip)
* [TestMu AI Tunnel for macOS](https://downloads.lambdatest.com/tunnel/v3/mac/64bit/LT_Mac.zip)
* [TestMu AI Tunnel for Linux](https://downloads.lambdatest.com/tunnel/v3/linux/64bit/LT_Linux.zip)

Open command prompt and navigate to the binary folder.

Run the following command:

```bash
LT -user {user’s login email} -key {user’s access key}
```
So if your user name is lambdatest@example.com and key is 123456, the command would be:

```bash
LT -user lambdatest@example.com -key 123456
```
Once you are able to connect **TestMu AI Tunnel** successfully, you would just have to pass on tunnel capabilities in the code shown below :

**Tunnel Capability**

```
"tunnel" = true
```

## Tutorials 📙

Check out our latest tutorials on pytest automation testing 👇


* [Basics Of The pytest Framework](https://www.testmuai.com/blog/selenium-python-pytest-testing-tutorial/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)
* [Setting Up pytest: Installation And Getting Started](https://www.testmuai.com/blog/test-automation-using-pytest-and-selenium-webdriver/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)
* [Pytest testing Using Selenium WebDriver](https://www.testmuai.com/blog/selenium-webdriver-with-python/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)
* [Parallel Testing With pytest Selenium](https://www.testmuai.com/blog/pytest-tutorial-parallel-testing-with-selenium-grid/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)
* [Parameterization In Selenium pytest](https://www.testmuai.com/blog/parameterization-in-pytest-with-selenium/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)
* [Automated Browser Testing With Selenium pytest Fixtures](https://www.testmuai.com/blog/end-to-end-tutorial-for-pytest-fixtures-with-examples/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)
* [Executing Multiple Test Cases From Single File](https://www.testmuai.com/blog/pytest-tutorial-executing-multiple-test-cases-from-single-file/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)
* [How To Stop Test Suites After ‘N’ Test Failures](https://www.testmuai.com/blog/how-to-stop-test-suite-after-n-test-failures-in-pytest/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)
* [Generating Test Reports In Selenium pytest](https://www.testmuai.com/blog/pytest-report-generation-for-selenium-automation-scripts/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)


Please refer to our [PyTest Tutorial | Selenium With Python | Learn PyTest In 90 minutes | TestMu AI](https://www.youtube.com/watch?v=UzkuOACmBpA). ▶️

Subscribe To Our [TestMu AI YouTube Channel 🔔](https://www.youtube.com/@TestMuAI) and keep up-to-date on the latest video tutorial around software testing world.

## Documentation & Resources :books:

      
Visit the following links to learn more about TestMu AI's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

* [TestMu AI Documentation](https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)
* [TestMu AI Blog](https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)
* [TestMu AI Learning Hub](https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample)    

## TestMu AI Community :busts_in_silhouette:

The [TestMu AI Community](https://community.testmuai.com/?utm_source=github&utm_medium=repo&utm_campaign=pytest-selenium-sample) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎

## What's New At TestMu AI ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.lambdatest.com/)

## 🚀 LambdaTest is Now TestMu AI

👋 Welcome to TestMu AI, the next evolution of LambdaTest. As of January 2026, [LambdaTest is Now TestMu AI](https://www.testmuai.com/lambdatest-is-now-testmuai/) - we have evolved from a cross-browser testing cloud into a unified, AI-native quality engineering platform designed for the modern DevOps era.

Whether you have been part of the LambdaTest community for years or are just discovering TestMu AI, our mission remains the same: to help you ship faster with high-scale test execution, autonomous testing, and deep quality analytics.

### 🔄 Our Rebrand Journey

In 2017, we introduced LambdaTest with a clear mission: to become the world's most trusted cloud testing platform. We built a scalable, high-performance test cloud that eliminated flakiness, improved developer feedback cycles, and accelerated release velocity for teams worldwide.

As LambdaTest grew, we expanded the platform into Test Intelligence, Visual Regression Testing, Accessibility Testing, API Testing, and Performance Testing, covering the entire testing lifecycle. These capabilities enabled teams to test any stack, on any technology, at enterprise scale.

Over time, we rebuilt the architecture to be AI-native from the ground up. What began as LambdaTest's high-performance testing cloud has now evolved into TestMu AI, an AI-native, multi-agent platform redefining modern quality engineering.

We chose the name TestMu AI to reflect our shift towards intelligent, autonomous testing. While our identity has changed, our core technology and commitment to the testing community stay the same.

👉 Find [LambdaTest's New Home](https://www.testmuai.com/).

### 🔭 Explore TestMu AI

The same infrastructure LambdaTest customers relied on, now delivered through autonomous AI agents.

- [KaneAI](https://www.testmuai.com/kane-ai/)
- [Agent-to-Agent Testing](https://www.testmuai.com/agent-to-agent-testing/)
- [HyperExecute](https://www.testmuai.com/hyperexecute/)
- [Real Device Cloud](https://www.testmuai.com/real-device-cloud/)
- [Pricing](https://www.testmuai.com/pricing/)
- [Documentation](https://www.testmuai.com/support/docs/)