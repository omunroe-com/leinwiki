Here is how I ([dcj](https://github.com/dcj)) install Leiningen in the Jenkins CI server, and use it to build my Clojure projects.

I'm not claiming this is the only way to do so, or the best, but it documents how I have gotten this to work fairly well.
I am very interested in ideas/suggestions about how to do this better....

I am working with another developer to produce a Leiningen plugin for Jenkins, here is the 
[requirements document](http://likestream.github.com/doc/leiningen-jenkins-requirements.html).  Maybe by May or June (2011) this will be available.

In the mean time, here is how I install and use Leiningen with Jenkins using existing Jenkins features and plugins:

First I create a Jenkins job that downloads and installs Leiningen into the Jenkins workspace.
[[http://likestream.github.com/doc/screenshots/lein-jenkins/DefininingLeiningenInstallProject.png|frame]]

Next I configure how to get the stable release of Leiningen from GitHub:
[[http://likestream.github.com/doc/screenshots/lein-jenkins/GetLeiningenStableFromGitHub.png|frame]]

And how often to poll for new versions:
[[http://likestream.github.com/doc/screenshots/lein-jenkins/LeiningenBuildTrigger.png|frame]]

Then I set up environment variables for this job. (Note that this requires the SetEnv Jenkins plugin.)
[[http://likestream.github.com/doc/screenshots/lein-jenkins/LeiningenInstallEnvVars.png|frame]]

I am building on Solaris, so I need to make sure /usr/ucb in on my path so lein can find whoami.
In addition, Leiningen puts jar files into $HOME/.lein, so I have found it helpful to make sure $HOME is defined.
Next I configure how to install Leiningen:
[[http://likestream.github.com/doc/screenshots/lein-jenkins/LeiningenInstallBuildSteps.png|frame]]

Now that the install is done, archive the results:
[[http://likestream.github.com/doc/screenshots/lein-jenkins/LeiningenInstallArchive.png|frame]]

OK, so now Leiningen should be downloaded, installed, and available for use, here is how I access lein when configuring 
a Clojure build job in Jenkins, first define any important environment variables:
[[http://likestream.github.com/doc/screenshots/lein-jenkins/BuildWithLeinEnvVars.png|frame]]

(For this next step, make sure you've installed the Copy Artifacts plugin.) The first, (or one of the early) build steps should be to "Copy Artifacts From Another Project", and configure it to copy the lein script you downloaded previously into the workspace of this new project (I put it in ./bin):
[[http://likestream.github.com/doc/screenshots/lein-jenkins/GetLeiningenFromInstallJob.png|frame]]

Subsequent build steps can be "Execute Shell", and then just issue the lein "target" command(s) you want.

