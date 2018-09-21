# node-boilerplate

This is quick starting point to clone and start node project. Mainly for my own learning purposes. 
However this can help beginners to setup quickly "standardized" layout and set of "tooling/development" modules.

## Goals and Features 


Tools:

- tests - including selected test runner and libs 
- lints and other code quality tools
- unobtrusive - tools are installed as devDependencies, not --global and used with `npm run` scripts
- security checks - of own code and dependencies as well

Libraries:

- Promises - since we code in promise style, good lib was needed, we have chosen bluebird.

## Branches

There are several branches created. The goal is to test if we can
create template for different types of projects (adding modules, dev-modules, samples)
and keep them updated from master branch by simple git merges.

Branches:

- cli-boilerplate - quickly create command line tools, using node.js
- d3-boilerplate - create d3 charts (web, cli)


## Using

To create new project based on the node-boilerplate just run:

	# sample name
	NAME=my-cool-project
	TEMPLATE=cli-boilerplate

Then run:

	git clone -b $TEMPLATE --single-branch https://github.com/ainthek/node-boilerplate.git $NAME
	cd $NAME
	git remote rename origin node-boilerplate
	git branch -m $TEMPLATE master

	sed -i "s;node-boilerplate;$NAME;" package.json
	echo "# $NAME" > README.md

	npm install
	npm test


### To update your project with template

	git fetch node-boilerplate; git merge node-boilerplate/cli-boilerplate master

## Tools Installed

You can do the following:

Run Lints and Code Analysis 

	npm run mocha
	npm run lint
	npm run plato


Run tests

	npm test


With npm 2.0 you can also run tests (and any other scripts) 
with ad-hoc params, e.g changing reporter of test on CLI, 
without touching package.json scripts or mocha.opts

	npm run test -- -R dot


## Notes 

Useful commands used when creating this boilerplate, and few notes:

	npm init
	

	# git setup

	touch .gitignore
	echo "node_modules" 	>> .gitignore
	echo "npm-debug.log" 	>> .gitignore


	# lints

	npm install --save-dev JSHint
	touch .jshintignore
	touch .jshintrc
	echo "node_modules/" 	>> .jshintignore

	npm install --save-dev plato
	echo "test_reports/" 	>> .gitignore
	echo "test_reports/" 	>> .jshintignore


	# tests

	npm install --save-dev mocha

	mkdir test
	touch test/mocha.opts

	# you may also want this:

	# as assert library for tests
	npm install --save-dev chai-as-promised

	# for load tests
	npm install --save-dev loadtest


	# libs
	npm install --save bluebird|name|version|homepage|description|path|




