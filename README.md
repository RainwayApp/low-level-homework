# Take-home assignment: data processing pipeline
Rust/C/C++ project to implement a multi-thread aware data processing pipeline.

## Project Description
Design and implement a framework for a data processing pipeline using Rust, C or C++ (see Wikipedia's description of data processing pipeline). This framework should be general enough to make it applicable to any number of scenarios. It should also be capable of taking advantage of a multi-core operating environment (i.e. multi-threaded data processing). So basically, the framework should make it possible to hook together an arbitrary and custom set of data processing elements to process, a potentially, large data set efficiently. Each data processing element, or node, in the pipeline receives input, processes it, and produces output which is then processed by another node or set of nodes.

## Functional and Non-Functional Requirements

* Only standard Rust, C, or C++17 code should be used.
* No 3rd party libraries.
* Should support multi-threaded processing.
* Should support 1 to many on output. In other words the output of a single data processor can be used as input to more than 1 data processor.
* Should support many to 1 on input. A single processor can receive input from multiple processors.
* Should support any type of data as input or output.
* The framework's public interfaces should be documented with code comments.

## Project Application
In addition to creating a data processing pipeline framework, you should use this framework to create an application that reads an arbitrary number of PCM audio files and produces an output file that is a multi-channel interleaved PCM audio file with a certain amount of gain (i.e. volume increased) applied. Each channel of output comes from one of the input files. Furthermore, the output may need to be converted to a different data type on output, the possible input and output data types being either 32 bit floating point or 16 bit integer.

The application should be a command line executed program that takes as input a path to a directory containing the PCM files, a number indicating the amount of input files in the directory, a string indicating the type of data in the input files (float or int), a number indicating the amount of decibels to add, and a string indicating the type of output (float or int).

So for example consider an input directory:

```
input/
  0.pcm
  1.pcm
```

Then if the application was run like this: ./app input 2 int 5 float

It would read 0.pcm and 1.pcm as an array of 16 bit integers and then produce an interleaved dual channel output file in floating point format that is 5 decibels louder than the input.

Couple of assumptions:

* The input files will be named in an orderly fashion, i.e. if there are three input files they will be named 0.pcm, 1.pcm, 2.pcm.
* The input files are just binary files consisting of an array of either 32 bit floating point numbers or 16 bit integers.

The primary goal of the project is to demonstrate understanding of your chosen systems programming language and its standard libraries and multi-threaded programming, and to demonstrate the ability to learn new technologies and/or techniques. Feel free to google as much as you need to in order to figure out what you need to figure out.

When you have completed the project, create a repo on your personal account and push the source code and the necessary files to build the code and run it, then link it to us in an email to work-at [AT] rainway.com. Build files can be an XCode workspace, Visual Studio solution, CMake, or even old school GNU Makefiles.
