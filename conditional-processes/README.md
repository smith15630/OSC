# Conditional process execution 

## Problem 

Two different tasks need to be executed in a mutually exclusive manner, 
then a third task should post-process the results of the previous execution.

## Solution

Use a [when](https://www.nextflow.io/docs/latest/process.html#when) statement to conditionally 
execute the two processes, having each of them to declare two different output channels.

Then use the [mix](https://www.nextflow.io/docs/latest/operator.html#mix) to create 
a new channel that holds the outputs produced by the two process and use it as the input
for the third process.

## Code 

[Click here](main.nf) 

## Run it

Use the the following command to execute the example:

    nextflow run main.nf

The processes `foo` and `omega` are executed. Run the same command 
with the `--flag`` command line option. 

    nextflow run main.nf --foo 

This time the processes `bar` and `omega` are executed.       
