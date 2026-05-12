# Run Selenium Tests With C# — TestMu AI (Formerly LambdaTest)

![image](https://user-images.githubusercontent.com/70570645/171429042-610e8f3d-d2a4-4896-8bdb-8aeed87e0ce7.png)

*Learn how to run C# Tests using TestMu AI Grid.*


<p align="center">
  <a href="https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/certifications/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/@TestMuAI" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

[<img height="58" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium)


## Table of Contents:


* [Prerequisites](#prerequisites)
* [Run Your First Test](#run-your-first-test)
* [Parallel Testing With C#](#running-your-parallel-tests-using-c#-testing-framework)
* [Local Testing With C#](#testing-locally-hosted-or-privately-hosted-projects)



## Prerequisites


Before you can start performing **C#** automation testing with **Selenium**, you would need to:

* Download and install **Selenium WebDriver** from its [official website](https://www.selenium.dev/downloads/).
* Make sure you have the latest version of C#.
* **.Net** framework to deliver guidelines while developing a range of application using C#.
* Download [Selenium WebDriver Language Binding](https://www.selenium.dev/downloads/) for C# and extract them to appropriate folder. A [.NET Core SDK](https://dotnet.microsoft.com/en-us/download) of 2.1 or greater version.

### Installing Selenium Dependencies And Tutorial Repo

**Step 1:** Clone the TestMu AI CSharp-NUnit-Selenium GitHub repository and navigate to the code directory as shown below:

```
git clone https://github.com/LambdaTest/CSharp-Selenium-Sample
cd CSharp-Selenium-Sample
```

### Setting up Your Authentication

Make sure you have your TestMu AI credentials with you to run C# automation scripts. You can obtain these credentials from the [TestMu AI Automation Dashboard](https://automation.lambdatest.com/login?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium) or by your TestMu AI Profile.

**Step 2:** Set TestMu AI Username and Access Key in environment variables.

 **For Linux/macOS**:
 
 `export LT_USERNAME="YOUR_USERNAME" export LT_ACCESS_KEY="YOUR ACCESS KEY"`
 
 **For Windows**:
 
 `set LT_USERNAME="YOUR_USERNAME" set LT_ACCESS_KEY="YOUR ACCESS KEY"`


## Run Your First Test

>**Test Scenario**: Checkout sample NUnitSeleniumTests.cs file. This NUnit Selenium script tests a sample to-do list app by marking couple items as done, adding a new item to the list and finally displaying the count of pending items as output.

**Step 3:** Navigate to [singleTest.cs](https://github.com/LambdaTest/CSharp-Selenium-Sample/blob/master/NUnitSelenium/NUnitSeleniumTests.cs) using VSCode. Copy and replace this code in the singleTest.cs file in the project you opened in the previous step.

### Configuration of Your Test Capabilities

**Step 4:** In the test script, you need to update your test capabilities. In this code, we are passing browser, browser version, and operating system information, along with TestMu AI Selenium grid capabilities via capabilities object. 

The capabilities object in the above code are defined as:

```
 ChromeOptions capabilities = new ChromeOptions();
            capabilities.BrowserVersion = 'latest';
            Dictionary<string, object> ltOptions = new Dictionary<string, object>();
            ltOptions.Add("username", LT_USERNAME);
            ltOptions.Add("accessKey", LT_ACCESS_KEY);
            ltOptions.Add("platformName", "Windows 10");
            ltOptions.Add("project", "Demo LT");
            ltOptions.Add("w3c", true);
            ltOptions.Add("plugin", "c#-c#");
            capabilities.AddAdditionalOption('LT:Options', ltOptions);
```

**Note:** You can generate capabilities for your test requirements with the help of **[Desired Capabilitiy Generator](https://www.testmuai.com/capabilities-generator/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium)**.

### Executing the Test
* Single Test
```bash
dotnet run single
```
* Parallel Tests
```bash
dotnet run parallel
```

### Executing in Linux/macOS

 * Install dotnet runtime from https://dot.net/v1/dotnet-install.sh
 
 ```bash
  chmod +x ./dotnet-install.sh;
  ./dotnet-install.sh --version latest;

 ```

Your results would be displayed on the test console and on the TestMu AI Automation Dashboard.


## Running Your Parallel Tests Using dotnet runtime 
 
 **Executing  parallel tests in Windows/Linux/MacOS**
 
```bash
dotnet run parallel
```
Your results would be displayed on the test console and on the TestMu AI Automation Dashboard.


## Testing Locally Hosted Or Privately Hosted Projects

You can test your locally hosted or privately hosted projects with TestMu AI Selenium grid using TestMu AI Tunnel. All you would have to do is set up an SSH tunnel using tunnel and pass toggle `tunnel = True` via desired capabilities. TestMu AI Tunnel establishes a secure SSH protocol based tunnel that allows you in testing your locally hosted or privately hosted pages, even before they are live.

Refer our [TestMu AI Tunnel documentation](https://www.testmuai.com/support/docs/testing-locally-hosted-pages/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium) for more information.

Here’s how you can establish TestMu AI Tunnel.

Download the binary file of:
* [TestMu AI Tunnel for Windows](https://downloads.lambdatest.com/tunnel/v3/windows/64bit/LT_Windows.zip)
* [TestMu AI Tunnel for macOS](https://downloads.lambdatest.com/tunnel/v3/mac/64bit/LT_Mac.zip)
* [TestMu AI Tunnel for Linux](https://downloads.lambdatest.com/tunnel/v3/linux/64bit/LT_Linux.zip)

Open command prompt and navigate to the binary folder.

Run the following command:

```bash
LT -user {username} -key {user’s access key}
```
So if your user name is lambdatest@example.com and key is 123456, the command would be:

```bash
LT -user lambdatest-username -key 123456
```
Once you are able to connect **TestMu AI Tunnel** successfully, you would just have to pass on tunnel capabilities in the code shown below :

**Tunnel Capability**

```c#
ltOptions.Add("tunnel", true);      
```


## Tutorials 📙

Check out our latest tutorials on Selenium NUnit 👇

* [NUnit Environment Setup](https://www.testmuai.com/blog/setup-nunit-environment-with-visual-studio/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium)
* [NUnit With Selenium](https://www.testmuai.com/blog/nunit-testing-tutorial-for-selenium-csharp/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-NUnit-Selenium)
* [Selenium WebDriver Commands in NUnit](https://www.testmuai.com/blog/top-28-selenium-webdriver-commands-in-nunit-for-test-automation/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-NUnit-Selenium)
* [NUnit Parameterized Unit Tests](https://www.testmuai.com/blog/nunit-parameterized-test-examples/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-NUnit-Selenium)
* [NUnit Asserts](https://www.testmuai.com/blog/asserts-in-nunit/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-NUnit-Selenium)
* [NUnit Annotations](https://www.testmuai.com/blog/nunit-annotations-for-selenium-automation/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-NUnit-Selenium)
* [Generating Test Reports In NUnit](https://www.testmuai.com/blog/report-in-nunit/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-NUnit-Selenium)
* [Parallel Execution In NUnit](https://www.testmuai.com/blog/parallel-execution-with-specflow-nunit-and-selenium/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-NUnit-Selenium)

For video tutorials on Selenium NUnit, please refer to our [NUnit Tutorial Playlist](https://www.youtube.com/playlist?list=PLZMWkkQEwOPkg_-aMxUHDUp5DF_zQ5xxK). ▶️

Subscribe To Our [TestMu AI YouTube Channel 🔔](https://www.youtube.com/@TestMuAI) and keep up-to-date on the latest video tutorial around software testing world.


## Documentation & Resources :books:

Visit the following links to learn more about TestMu AI's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

* [TestMu AI Documentation](https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium)
* [TestMu AI Blog](https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium)
* [TestMu AI Learning Hub](https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium)     


## TestMu AI Community :busts_in_silhouette:

The [TestMu AI Community](https://community.testmuai.com/?utm_source=github&utm_medium=repo&utm_campaign=CSharp-Selenium) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎


## What's New At TestMu AI ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.testmuai.com/) 
      

## 🚀 [LambdaTest is Now TestMu AI](https://www.testmuai.com/lambdatest-is-now-testmuai/)

👋 Welcome to TestMu AI, the next evolution of LambdaTest. As of January 2026, LambdaTest has officially rebranded to TestMu AI. We have evolved from a cross-browser testing cloud into a unified, AI-native quality engineering platform designed for the modern DevOps era.

Whether you have been part of the LambdaTest community for years or are just discovering TestMu AI, our mission remains the same: to help you ship faster with high-scale test execution, autonomous testing, and deep quality analytics.

**🔄 Our Rebrand Journey**

We chose the name TestMu AI to reflect our shift towards intelligent, autonomous testing. While our identity has changed, our core technology and commitment to the testing community stay the same.

**✨ Specialties**

- 🤖 AI-Native Test Execution (Formerly LambdaTest)
- ⚡ Autonomous Test Automation
- 🌐 Cross-Browser & Mobile Testing
- 📊 Unified Quality Intelligence

👉 Find [LambdaTest's New Home](https://www.testmuai.com/).
