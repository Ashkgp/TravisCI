# TravisCI

Continuous Integration is a practice of merging all working copies to a shared repo.
Travis CI helps to validates the pull requests from contributors before merging it with the master repo.

It helps avoid Integration hell and breaking of code in master repo.

##Integrating TravisCI

###Test ROS Integration on Travis
Requires Ubuntu 14.04 and ROS Indigo for successful build ( can be changed later )

- Sign in to [TravisCI](http://travis-ci.org) with your [GitHub](https://github.com) account , accepting all the access permissions.

- Once signed in, go to profile page on [TravisCI](http://travis-ci.org) and enable Travis CI for repository you want to build.

- Add a <code>.travis.yml</code> file to the repository with following format for build
```sh
dist:trusty
sudo:required
language:
	-generic
cache:
	-apt
env:
	global:
		-(Declare all global variables required for the build)
before_install:
	- (All the commands need to be run on the virtual machine to build the code)
install:
	- (Setting up the workspace and sourcing the required variables )
	- ( Making the project )
before_script:
	- ( Optional install )
script:
	- ( Sourcing the variables )
	- ( Making the project )
	- ( Run test results )
```

- Add ROS code you want to build.

- Add the <code>.travis.yml</code> file to git, commit and push to trigger the TravisCI

- Check the TravisCI page to check the build status.

