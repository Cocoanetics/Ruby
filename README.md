Cocoanetics Ruby
================

Collection of my Ruby Scripts

###Coveralls.rb 

This script finds all **.gcda** files unterneath the current user's DerivedData folder. Since you get a fresh VM every time Travis-CI builds those should be the ones that you also want to submit.

Submission is done with [cpp_coveralls](https://github.com/eddyxu/cpp-coveralls)

Example **.travis.yml**

	---
	language: objective-c

	before_script:
	  - sudo easy_install cpp-coveralls

	script:
	  - xctool -project DTFoundation.xcodeproj -scheme "Static Library" build test -sdk iphonesimulator

	after_success:
	  - ./coveralls.rb
	  
It would be great if I could add some command line options to pass onto the cpp-coveralls.
