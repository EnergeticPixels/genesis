# <center>GENESIS</center>
#### <center>For all new beginnings</center>

This is a project of my own. Mainly "GULP" way of doing things. Express/MongoDB (Mongoose) server/API. Front-end will be ejs/jade or ReactJS and Bootstrap (3 or 4) embedded.

I intend this to be a starting point for new projects both APIs and front-ends such as D3, scenejs, threejs, babylonjs projects with combined unit and end-to-end testing frameworks such as mocha, chai, and phantomjs.

I will try to keep with the spirit of TDD/BDD way of development as much as possible.

Don't reinvent the wheel. This project will pull in ideas and proven methodologies from others who have done some of the leg work already. IE., I have limited hair on my head, don't remove any more.

Global installs before working with this project:<br /><i>npm install -g node-inspector bower gulp

##Slamming the start:
- npm install
- bower install
- gulp serve-dev

#Tasks

##### <center><u>Need to solidify everything below this line
##Listing
- gulp help
displays all of the available gulp tasks

##Analysis
- gulp vet
Performs static code analysis on all js files. runs jshint and jscs.
- gulp vet --verbose
displays all files affected and extended information about this code analysis.
- gulp plato
performs code analysis using plato on all js files. Plato gens a report in the reports folder.

##Testing
- gulp serve-specs
Serves and broses to the spec runner html page and runs the unit tests in it. injects any changes on the fly and reruns the tests. Quick and easy view of the tests not in the termical.
- gulp test
runs all unit tests using karma runner, mocha, chai and sinon with phantomjs. depends on vet task for code anal.
- gulp test --startServers
runs all unit tests and midway tests. cranks up a second node process to run server for midway tests to hit a web api.
- gulp autotest
runs a watch to run all unit tests
- gulp autotest --startServers
runs a watch to run all unit tests and midway tests. cracks up a second node process to run a server for the midway tests to hit api.

##cleaning
- gulp clean
remove all files from teh build and temp folders so that you can rebuild fresh
- gulp clean-images
remove all images from the build folder
- gulp clean-code
remove all js and html from the build folder
- gulp clean-fonts
remove all fonts from teh build folder
- gulp clean-styles
remove all styles fromt eh build folder

##Fonts-Images
- gulp fonts
copy all fonts from source to build folder
- gulp images
copy all images from source to build folder

##Styles
- gulp styles
compile LESS files to CSS add vendor prefixes and copy to build folder

##Bower
- gulp wiredep
looks up all bower components' main files and js source code, then adds them to the index.html.  bowerrc runs this as a postinstall task whenever bower install is run.

##Angular
- gulp templatecache
creates an angularmodulethat adds all html templates to angular's $templatecache. this pre-fetches all html templates saving server round-trips for thml.
- gulp templatecache --verbose
displays all files affected by the task

##Serving development code
- gulp serve-dev
serves the development code and launches it in a broswer with goal of building for development is to do it as fast as possible to keep development efficient. this task serves all code from the source folders and compiles less to css in a temp folder
- gulp serve-dev --nosync
serves the development code without launching the browser
- gulp serve-dev --debug
launch debugger with node-inspector
- gulp serve-dev --debug-brk
launch debugger and break on 1st line with node-inspector
- gulp serve-dev --stubs
serves the development code with the stubs to avoid hitting a real backend

##Building Production
- gulp html
optimize all js and styles, move to a build folder, and inject them into new index.htm
- gulp build
copies all fonts, images and runs gulp html to build the production code to the build folder

##Serving Production
- gulp serve-build
serve the optimized code from the build folder and launch it in a broswer
- gulp serve-build --nosync
serve the optimized code from build folder and manually launch the broswer
- gulp serve-build --debug
launch debugger with node-inspector
- gulp serve-build --debug-brk
launch debugger and break on 1st line with node-inspector
