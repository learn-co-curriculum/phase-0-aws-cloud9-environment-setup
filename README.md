# AWS Cloud9 Environment Setup

## Introduction

The following instructions are for setting up AWS Cloud9, a cloud-based
Integrated Development Environment. These instructions are provided as an
alternative to setting up a local environment on your personal computer. If you
have not attempted to set up your local environment, we recommend trying to do
so now before continuing:

- [MacOS Environment Instructions](https://github.com/learn-co-curriculum/environment-mac-os-catalina-setup)
- [Windows 10 WSL2 Environment Instructions](https://github.com/learn-co-curriculum/wsl2)

If you attempted the instructions for your operating system but ran into issues
with setup, AWS Cloud9 can serve as a temporary environment and will allow you
to complete and store your Flatiron School coding work in your browser.

## Important Notices

The AWS Cloud9 IDE shoud only be used as a temporary environment solution. Later
portions of our course content require you to have a local environment. The principal
value of using the Cloud9 IDE is that it will allow you to maintain pace with
your cohort while working on the early course content. We recommend that you
continue to try and get your own local environment set up during this time.

Using the Cloud9 IDE requires a credit card and may incur charges from AWS if
used for an extended period of time. If you are a new AWS customer, you will
have access to the AWS Free Tier, providing the Cloud9 IDE for free for 12
months. There are some [resource limits][], including a limit of 750 hours of
use per month. Although we don't expect you to hit this limit (750 hours divided
by 30 days is 25 hours per day), [AWS provides an example of what pricing might
look like][aws pricing], should you hit a limit.

## Getting Started

Before we start setting up Cloud9, you will need both a [GitHub][] account and
[Flatiron School][] account. You will also need to connect your GitHub account
with your Flatiron School account. To do this, go to the [Flatiron School][]
website, click on your avatar in the upper right corner of the page, then click
**Manage Account**. You can also access this page using the direct URL,
[https://learn.co/account](https://learn.co/account).

<img src="https://curriculum-content.s3.amazonaws.com/environment-setup/learn-co-manage-account-menu.png" height=200>

Once you are on the **Account Management** page, click **Connected Apps**.

<img src="https://curriculum-content.s3.amazonaws.com/environment-setup/learn-co-connect-apps-nav-button.png" height=50>


From here, click the **Connect Account** button to connect your GitHub Account.

If connected successfully, your browser will redirect you to the [Flatiron
School][] landing page. If you head back to the [Connected Apps][] you will see
your GitHub account name is displayed.

## Setting Up Your AWS Account

With your Flatiron School and GitHub accounts set up, the next step is to sign
up for your AWS Account and get access to the Cloud9 IDE. Got to
[https://aws.amazon.com/cloud9/][cloud9] and click **Get Started with AWS
Cloud9**.

![cloud9 get started button](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-get-started-button.png)

You will first need to set up an AWS account. Fill out the required account and
credit card billing information. Once you have set up your account, head back to
theh [cloud9 landing page][cloud9] and click **Sign in to the Console** in the
upper right.

<img src="https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-sign-in-to-console.png" height=50>

The AWS Management Console will load. In the **Find Services** search bar,
search for `Cloud9`.

![find cloud9](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-find-services-aws.png)

Clicking on the Cloud9 result will bring you to your Cloud9 homepage. The URL
will be unique, depending on what AWS servers are hosting your IDE. We recommend
bookmarking this page to get back to it easily. If you have already created a
Cloud9 IDE, the environment instance will be listed here. In our case, we
want to click the **Create environment** button.

<img src="https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-create-environment-button.png" height=50>

AWS will prompt you to give your environment a name and an optional
description. Click **Next Step** when ready.

![cloud9 name and description](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-environment-name-and-description.png)

After naming the environment, you will need to select the Environment type and
Instance type. Choose **Create a new EC2 instance for environment (direct
access)** for Environment type. For Instance type, choose **t2.micro(1 GiB RAM +
1 vCPU)**. This is the only Instance type eligible for the AWS free-tier but is
more than enough processing power for our purposes.

![cloud9 environment and instance settings](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-environment-and-instance-settings.png)

Below these options, you'll have a choice of Platform and Cost-saving settings.
Leave the default options - **Amazon Linux** and **After 30 minutes**. Click
**Next Step** to move on.

![cloud9 platform and cost savings options](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-platform-and-cost-savings.png)
)

On the final page, you will have a chance to review your settings.

![cloud9 environment review page](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-environment-settings-review-page.png)

If everything looks correct, click **Create environment**. Your new Cloud9 IDE
will load in the browser window. It may take a few minutes for AWS to configure
everything.

When everything is loaded, you should see an AWS Cloud9 welcome page.

## Exploring the Cloud9 IDE

The Cloud9 IDE is divided into three main sections.

- On the left side of the screen is your directory navigation. As you work on
  various assignments, this section will become populated with files and
  folders.

  <img src="https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-directory-navigation.png" height=200>

- Along the bottom of the page is a terminal. You will use this terminal to
  write and execute commands. Click the terminal, type `echo "hello world!"`,
  and press `enter` / `return` to test it out. The terminal will print out `hello
  world!` in response.

  ![cloud9 terminal example](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-terminal-example.png)

- The IDE's central section (where you see the welcome page) is will display
  file contents. Clicking on files in the directory navigation will open them up
  in this section.

  ![cloud9 file contents sections](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-nav-and-file-contents.png)

> **Note:** If you would like more space to type in your terminal or view file
> contents, you can click and drag the border just above the terminal to adjust
> the height of both.

Now that you have your Cloud9 IDE up and running, it is time to do some
configuration for this course.

## Configuring the Cloud9 IDE

For the first part of this course, we need to install two tools, also known as
Ruby gems. The first gem is `learn-co`, Flatiron School's tool for testing and
submitting work. To install, type the following into the terminal:

```sh
gem install learn-co
```

The terminal will indicate several items are being installed.

![learn-co gem installing](https://curriculum-content.s3.amazonaws.com/environment-setup/learn-co-gem-install.png)

When finished, it will display `24 gems installed`.

![learn-co gem install success](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-learn-gem-install.png)

The second gem we need to install is `bunder`. To install, type the following
into the terminal:

```sh
gem install bundler
```

Similar to the `learn-co` gem, you will see a message `1 gem installed` once
the installation is complete.

## Configuring the Learn Gem

Next, we need to set up the `learn-co` gem so that it can connect to your
Flatiron School account.

In your Cloud9 terminal, run `learn whoami`. You will see a message that you
need an OAuth token to connect to the Learn web application.

![learn-co oauth prompt](https://curriculum-content.s3.amazonaws.com/environment-setup/learn-gem-oauth-prompt.png)

You can access this token from your account page on Flatiron School's website by
going to `https://portal.flatironschool.com/<your-github-username>`. Replace
`<your-github-username>` with your actual GitHub username.

> **Note:** The terminal message provides a URL example starting with
> `https://learn.co`. This URL is Flatiron School's older online platform and may
> not be available in the future. `https://portal.flatironschool.com/` should be
> used instead.

Scroll to the bottom of your account page. You should see a box that includes
**OAuth Token**, followed by a long set of letters and numbers

![learn-co oauth section](https://curriculum-content.s3.amazonaws.com/environment-setup/learn-co-oauth-section.png)

As noted on the page, this set of letters and numbers is unique to your account
and will be used to identify you, so do not share it with anyone. Select the
entire string of characters and copy it, then head back to the Cloud9 IDE.

In the terminal, paste in the copied letters and numbers and press enter /
return. The `learn-co` gem will display `Authenticating...`, then output the
name, username, and email associated with your Flatiron School account.

If you see your information displayed, you are all set.

## Testing Out Your Configuration

If your configuration is correct, you should be all set to start working on
Flatiron School assignments. This set of instructions will act as your
first assignment submission!

### Fork This Lesson

First, if you are not already there, go to Canvas and navigate to _this_ lesson.
You should be able to access this lesson from your Homeroom or Welcome course.

In the upper right corner of the lesson, you will see a **Fork** button. Click
this button.

<img src="https://curriculum-content.s3.amazonaws.com/fork-link.png" height=30>

If you have correctly configured your GitHub account and connected it to your
Flatiron School account, clicking **Fork** will open GitHub in a new browser
tab.

In this tab, you will see that GitHub is in the process of _forking_. Forking is
a process where an exact copy of a collection of code and files is created.
Clicking the **Fork** button copies the original version of an assignment over
to your personal GitHub account, then redirects you to that new copy. Having a
copy on your personal account allows you to write your own code solutions without
interfering with the original copy.

> **Note:** In GitHub, there is a Fork button as well. However, this button will
> not configure your fork with the necessary info for submitting to Canvas, so
> only use the **Fork** button in Canvas when working on assignments.

### Clone This Lesson to Your Environment

Once an assignment fork is created, you'll need to download it to your
environment. To do this, on your personal GitHub fork of the assignment, first,
click the **Code** button. A pop-up will appear that says Clone with HTTPS. You'll
see a URL provided starting with https://....

![clone from GitHub pop-up](https://curriculum-content.s3.amazonaws.com/git-clone-using-ssh.png)

**Before doing anything else**, make sure to switch from HTTPS to SSH by clicking
the Use SSH link. When clicked, the pop-up will change to display Clone with
SSH. Instead of a URL, you'll see what sort of looks like an email, starting
with git@github.com:.

![clone with ssh](https://curriculum-content.s3.amazonaws.com/canvas-welcome/clone-with-ssh.png)

From here, click the clipboard icon.

![clipboard icon](https://curriculum-content.s3.amazonaws.com/copy-clone-command-button.png)

Now, open your Cloud9 IDE. In the terminal, type `git clone`, then paste in what
you copied to your clipboard. It should look similar to the example below, but
with your GitHub username included:

```sh
git clone git@github.com:<your-username>/cloud9-aws-environment-setup.git
```

Press enter, and you should see a flurry of terminal activity. Once the terminal
gives you control to type again, a new folder with the assignment's GitHub name
will be present in the left navigation. Change directory into this folder to
access the assignment files.

```sh
cd cloud9-aws-environment-setup
```

### Completing and Submitting This Assignment

Most assignments will have tests that check your work and provide immediate
feedback in the terminal. We'll walk through some examples in upcoming lessons.

This assignment has a single test: check to see if you've correctly cloned this
assignment to your local machine. If you've followed the steps above, you've
completed everything you need to do to pass the test, all that is left to do is
run it.

To run an assignment's tests, make sure you're still in the assignment's folder
on your local machine, then type the following:

```sh
learn test
```

This command will again cause a flurry of activity in your terminal. After a few
moments, you should see the test results printed out. For this assignment, they
should look like this:

```sh
This assignment
    ✓ has been correctly cloned to your local environment


  1 passing (5ms)
```

Congratulations! You've passed the test! 

> **Note:** If you did not receive a passing test, or if your terminal produced
> some error, walk through the steps in this lesson again and make sure
> you've followed each one. If you're still receiving errors, we recommend going
> back to your Welcome course in Canvas and walking through the local
> environment setup instructions again to ensure everything is set up properly.

When all tests are passing, you can head back to the assignment on Canvas.
Refresh the assignment page, and you should see that Canvas now registers the
assignment as Complete, and you will be ready to move on to the next lesson.

![canvas submission success](https://curriculum-content.s3.amazonaws.com/environment-setup/canvas-submission-success.png)

Each assignment will be different and will include instructions on what is
required to complete it. Some labs will have many tests. You can run learn test
as many times as you'd like while working to solve these labs. You will submit
your work to Canvas each time you do, but Canvas will mark the assignment as
Incomplete until all tests are passing.

When finished, you should see a GitHub repo created on _your_ GitHub account.

## Conclusion

You've completed your Cloud9 environment setup and first assignment! You are now
set to complete assignments in this first phase of the course. Equipped with
this knowledge, you are now ready to tackle greater challenges!

## Resources

- [Flatiron School][]
- [GitHub][]
- [AWS Cloud9][cloud9]

[resource limits]: https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Types=*all
[aws pricing]: https://aws.amazon.com/cloud9/pricing/
[Connected Apps]: https://portal.flatironschool.com/account/github
[GitHub]: https://github.com/
[Flatiron School]: https://portal.flatironschool.com/
[cloud9]: https://aws.amazon.com/cloud9/
