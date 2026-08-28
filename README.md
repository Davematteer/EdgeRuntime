# EdgeRuntime

A small C++ runtime built around **V8**, Google's JavaScript engine.

The goal of this project is to learn how JavaScript runtimes work internally by embedding V8 into a C++ application and gradually building functionality around it.

## Goals

* Learn how to embed V8 in a C++ application
* Understand V8 isolates, contexts, handles, and handle scopes
* Expose C++ functions and objects to JavaScript
* Execute JavaScript from C++
* Understand how JavaScript and C++ communicate
* Learn more about runtime memory management and garbage collection
* Practice modern C++ and CMake
* Experiment with building a small custom JavaScript runtime

## Project Structure

```text
edgeruntime/
├── CMakeLists.txt
├── README.md
├── LICENSE
├── include/
├── src/
├── tests/
├── external/
└── build/
```

## Building

```bash
cmake -S . -B build
cmake --build build
```

## Current Status

Work in progress.

The project is currently focused on setting up V8 and learning the fundamentals of embedding the engine in a C++ application.

## Future Ideas

* Execute JavaScript files from the command line
* Expose custom C++ functions to JavaScript
* Create a small runtime API
* Implement console functionality
* Experiment with modules
* Explore asynchronous execution
* Build a simple command-line JavaScript runtime

## License

MIT
