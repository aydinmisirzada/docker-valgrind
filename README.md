## But...why?

[Valgrind](https://valgrind.org) is a great memory leak detection tool, but not available to MacOS Big Sur users at the moment. There's a workaround tho...

## Usage

Download the Dockerfile. Run:

`docker build -t docker-valgrind:0.1 .` 

to build the image. Now, you should be able to run the container using:

`docker run -tiv $PWD:/test docker-valgrind:0.1`

This will open interactive terminal session inside container and mount current working directory in `/test/`. Navigate to test directory: `cd test`. Compile and debug your code using `valgrind ./executable`
