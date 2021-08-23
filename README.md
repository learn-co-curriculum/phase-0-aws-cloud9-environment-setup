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

The AWS Cloud9 IDE should only be used as a temporary environment solution.
Later portions of our course content require you to have a local environment.
The principal value of using the Cloud9 IDE is that it will allow you to
maintain pace with your cohort while working on the early course content. We
recommend that you continue to try and get your own local environment set up
during this time.

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

<img src="https://curriculum-content.s3.amazonaws.com/environment-setup/learn-co-manage-account-menu.png" height="200px">

Once you are on the **Account Management** page, click **Connected Apps**.

<img src="https://curriculum-content.s3.amazonaws.com/environment-setup/learn-co-connect-apps-nav-button.png" height="50px">

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
the [cloud9 landing page][cloud9] and click **Sign in to the Console** in the
upper right.

<img src="https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-sign-in-to-console.png" height="50px">

The AWS Management Console will load. In the **Find Services** search bar,
search for `Cloud9`.

![find cloud9](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-find-services-aws.png)

Clicking on the Cloud9 result will bring you to your Cloud9 homepage. The URL
will be unique, depending on what AWS servers are hosting your IDE. We recommend
bookmarking this page to get back to it easily. If you have already created a
Cloud9 IDE, the environment instance will be listed here. In our case, we
want to click the **Create environment** button.

<img src="https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-create-environment-button.png" height="50px">

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

  <img src="https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-directory-navigation.png" height="200px">

- Along the bottom of the page is a terminal. You will use this terminal to
  write and execute commands. Click the terminal, type `echo "hello world"`,
  and press `enter` / `return` to test it out. The terminal will print out `hello world` in response.

  ![cloud9 terminal example](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-terminal-example.png)

- The IDE's central section (where you see the welcome page) will display
  file contents. Clicking on files in the directory navigation will open them up
  in this section.

  ![cloud9 file contents sections](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-nav-and-file-contents.png)

> **Note:** If you would like more space to type in your terminal or view file
> contents, you can click and drag the border just above the terminal to adjust
> the height of both.

Now that you have your Cloud9 IDE up and running, it is time to do some
configuration for this course.

## Configure the Cloud9 IDE

For the first part of this course, we need to install two tools, also known as
Ruby gems. The first gem is `learn-co`, Flatiron School's tool for testing and
submitting work. To install, type the following into the terminal:

```console
$ gem install learn-co
```

The terminal will indicate several items are being installed.

![learn-co gem installing](https://curriculum-content.s3.amazonaws.com/environment-setup/learn-co-gem-install.png)

When finished, it will display `24 gems installed` (the number of gems might
be slightly different depending on changes to these gems over time).

![learn-co gem install success](https://curriculum-content.s3.amazonaws.com/environment-setup/cloud9-learn-gem-install.png)

The second gem we need to install is `bundler`. To install, type the following
into the terminal:

```console
$ gem install bundler
```

Similar to the `learn-co` gem, you will see a message `1 gem installed` once
the installation is complete.

## Configure Git and GitHub

Git is the tool that we’ll use to download and upload the work that we do in
labs and lessons. To use Git without signing in every time, you can create a
Secure Shell (SSH) key and associate that to your GitHub account. Lastly, you
will want to run a few commands to make sure that when you use Git, you get the
proper credit for your work. This step will ask you to do work both in your
browser and your terminal.

## Action Items

**1.** Click on the terminal in the Cloud9 IDE

**2.** Type `git config --global color.ui true` and press `<Enter>`

**3.** Type `git config --global user.name` + `<Space>` + your name and press
`<Enter>` _(Note: this should be your full name, not your GitHub username, in
quotes.)_

**4.** Type `git config --global user.email` + `<Space>` + the email address you
used to sign up to GitHub and press `<Enter>`

**5.** Type `ssh-keygen` and press `<Enter>`

**6.** For each prompt **do not type anything**, just continue to press
`<Enter>`

**7.** Type `cat ~/.ssh/id_rsa.pub` and press `<Enter>`. Select and copy the
output, starting with `ssh-rsa`.

**8.** Open the [GitHub New SSH key form][]
(https://github.com/settings/ssh/new) _(Note: you need to be logged in to GitHub
to access that link.)_

**9.** Type "My Cloud9 IDE" in the "Title" input field

**10.** Paste what’s on your clipboard from step seven in the "Key" input field.
Each key is unique, but it should look something like this (notice the beginning
and end):

```console
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDWN9he+rGvUsQP
0vldUZT7Z/nTCPqFAPqjiDhNX0SxKdlWeTvhHXjqFRzy0K3cXpgxe0NR
/yLUphnFbsqCTzgLYTwMn/m8je/gOfPMtZcRuoOj69AJh5LM+TdLcFLZ
gL1sxjiLCcVO7Sn9ThTYEHSCsS6r2ZaTlFMfakeKBfH9pdWZHqR84pHP
aq3QxkkrWC7RGrPsBPTYjLYuy7d3Mjw+fUar2oeLUpmMjxX8Fqs7Qf5L
QR+4/MjA1PMVCVXSRDFUyDYZ756XBcnqQqyaJmSSfgSrk8OE3hqW
MDFerSP0tzgq26YBWnqsqmCTrSiDgHzgSyO7B8FizTUgn/okdD1b
ec2-user@ip-174-35-43-2
```

**11.** Click "Add SSH Key"

[github new ssh key form]: https://github.com/settings/ssh/new

### Check Your Work

If you see your new SSH key beneath the "SSH keys" heading, continue below.

## Connect Your GitHub Account to your Flatiron School Portal Account

Flatiron School has some helpful tools for you when working on your labs and
lessons through GitHub. For those tools to work, you will need to connect your
Flatiron School Portal account to your GitHub account.

### Action Item

1. Open the [Flatiron School Student Portal webpage][]
   (https://portal.flatironschool.com) _(Note: you need to be logged in to
   Flatiron School Student Portal.)_
2. Click on "Course" in the navigation bar at the top of the screen
3. Click the blue "Switch Materials" button in the dropdown
4. Click on the course that you are about to start
5. Open the [GitHub Account Management webpage][] (https://learn.co/account/github)
   _(Note: you may be asked to log in. Use your Flatiron School Student Portal
   username and password here.)_
   <!-- Note: this domain is not the Portal because of Canvas flows -->
6. Connect your GitHub account to your Flatiron School Portal account

[flatiron school student portal webpage]: https://portal.flatironschool.com
[github account management webpage]: https://learn.co/account/github

### Check Your Work

<iframe width="560" height="315" src="https://www.youtube.com/embed/mIzuVjiNre4" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

If you go back to the [GitHub Account Management webpage][]
(https://portal.flatironschool.com/account/github) and see a red "Disconnect"
button, continue below.

[github account management webpage]: https://portal.flatironschool.com/account/github

## Configure the learn-co gem on Cloud9

The learn-co gem is the tool that we’ll be using to test and submit the labs and
lessons that we’re working on. Before you can use it, you will need to connect
your Flatiron School Portal account to the copy of the learn-co gem on your
computer. This step will ask you to do work both in your browser and your
terminal.

### Action Item

1. Click on the terminal in the Cloud9 IDE
2. Type `touch ~/.netrc && chmod 0600 ~/.netrc` and press `<Enter>` _(Note: you may be asked to enter your password.)_
3. Type `learn whoami` and press `<Enter>` _(Note: don’t type anything here yet.)_
4. Go to your [Public Profile Management webpage][]
   (https://portal.flatironschool.com/account/profile) in your browser _(Note:
   if you’re not logged in, you will need to log in again.)_
5. Look for the "Username" heading and copy your username, but do not copy the
   text `https://learn.co/`
6. Go to your Flatiron School Student Portal Profile page
   ("https://portal.flatironschool.com/" + your username)
7. Scroll all the way to the bottom of the page to the heading "The information
   below is sensitive and unique to your account. Only you can view this
   information." with a red background.
8. Copy the string of characters under the "OAuth token" header
9. Paste the string of characters into the terminal and press `<Enter>`

[public profile management webpage]: https://portal.flatironschool.com/account/profile

### Check Your Work

<figure>
  <iframe width="560" height="315" src="https://www.youtube.com/embed/1eX_lwNfPCA" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
  <figcaption>Although this shows a local environment, your Cloud9 terminal should respond to the same commands seen in the video</figcaption>
</figure>

If you see a message with your name, username, and email, you should be all set.

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
[connected apps]: https://portal.flatironschool.com/account/github
[github]: https://github.com/
[flatiron school]: https://portal.flatironschool.com/
[cloud9]: https://aws.amazon.com/cloud9/
