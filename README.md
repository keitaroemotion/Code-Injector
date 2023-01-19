Code Injector (CNJ)
-------------------------

you need to put this under /usr/local/bin


What is this script for?
-------------------------
sometimes your project needs temporal code injection since the team doesn't want your stupid code for local debugging no one but you, yet it really matters to you.
For instance, no one wants your temporal settings configuration in your working directory or any other local code which helps you debug but not welcomed in the remote repo. 
Here this script saves you.

Installation
-------------------------
put this `cnj` script under /usr/local/bin or any other directory
which you can call from.

DSL
--------------------------
First you need to set the target working directory.
For instance if your workdir is /Users/joe/sampledir then
the example of the instruction dsl is:

```
dir: /Users/joe/sampledir 

file: src/to/file/Test.Java
  key: private def testMethod(
  ofs: 7
  text: ------

file: src/to/file/File.java 
  key: def getProductResult() {   
  ofs: 1 
  text: ------
```

This means you are going to change  either

```
/Users/joe/sampledir/src/to/file/Test.java
/Users/joe/sampledir/src/to/file/File.java
```

`key:` is the code position you want to inject your randome code into.

For instance, in File.java, if the script finds

```
def getProductResult() {   
```

then the text `------` is injected immediately after that line.


TODO: replacement, destroy the code in specific range etc...



