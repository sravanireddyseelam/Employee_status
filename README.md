#Getting Started
Newman is a command line Collection Runner for Postman. It allows you to run and test a Postman Collection directly from the command line. It is built with extensibility in mind so that you can easily integrate it with your continuous integration servers and build systems.

Newman maintains feature parity with Postman and allows you to run collections the way they are executed inside the collection runner in the Postman app.

#Installation and set up

Newman is built on Node.js. To run Newman, make sure you have Node.js installed.

You can download and install Node.js on Linux, Windows, and Mac OSX.

After you install Node.js, install Newman from npm globally on your system, which allows you to run it from anywhere.
```$ npm install -g newman```

Or navigate to the directory space where you want the newman to run.
```$ npm install  newman```


#Running the Collection form CLI

1. Clone the repo from github to your local

2. To run it the collection from local directory
```$ newman run mycollection.json```

3. To run the colletion by fetching it from github

```$ newman run  API-Employee-Status_collection.json -e Penguins_environment.json -g MyWorkspace_globals.json``

Options
Newman provides a rich set of options to customize a run. You can retrieve a list of options by running it with the -h flag.

$ newman run -h
Options:

Utility:
-h, --help                      output usage information
-v, --version                   output the version number

Basic setup:
--folder [folderName]           Specify a single folder to run from a collection.
-e, --environment [file|URL]    Specify a Postman environment as a JSON [file]
-d, --data [file]               Specify a data file to use either json or csv
-g, --globals [file]            Specify a Postman globals file as JSON [file]
-n, --iteration-count [number]  Define the number of iterations to run

Request options:
--delay-request [number]        Specify a delay (in ms) between requests [number]
--timeout-request [number]      Specify a request timeout (in ms) for a request

Misc.:
--bail                          Stops the runner when a test case fails
--silent                        Disable terminal output
--no-color                      Disable colored output
-k, --insecure                  Disable strict ssl
-x, --suppress-exit-code        Continue running tests even after a failure, but exit with code=0
--ignore-redirects              Disable automatic following of 3XX responses
Use the -n option to set the number of iterations to run the collection.

$ newman run mycollection.json -n 10  # runs the collection 10 times
