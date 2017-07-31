# interview-backend-histogram
Write a histogram builder!

# Overview
In order to identify threats for our customers, LogicHub analyzes customer data in a number of steps. You will write an application to visualize execution time statistics about each step.

You will write the following application: 

```
./<YOUR_APPLICATION_NAME> PATH_TO_JSON 
```

- Your application can be written in any major language (e.g. Java, Scala, Python, etc), but please package it in a way that makes it easy to compile / run it.
- The application is initialized with a path to a JSON file with runtime statistics for each step
- Your application should output a histogram with aggregate statistics about each step:

```
step3: (30s) ############################## 
step4: (15s) ###############
step1: (5s)  #####
step2: (1s)  #

```

# Input format
The input file contains a JSON object with a list of executions. Each object maps to a single execution of the LogicHub threat detection algorithm. Each object contains a `steps` object, which lists every single step and its execution time `timeMs` in milliseconds.

You can assume:
* Every execution will have the same steps for a given file.
* Each file will contain between 1 and 10,000 executions.
* The execution time is between 1ms and 2h.
* Each execution will have between 1 and 20 steps.

```json
{
 "executions":
  [
   {"id": 1,
    "steps": [
      {"name": "step1", "timeMs": 5000}, 
      {"name": "step2", "timeMs": 1000}, 
      {"name": "step3", "timeMs": 30000},
      {"name": "step4", "timeMs": 10000}]
   },
   {"id": 2,
    "steps": [
      {"name": "step1", "timeMs": 5000}, 
      {"name": "step2", "timeMs": 1000}, 
      {"name": "step3", "timeMs": 20000},
      {"name": "step4", "timeMs": 15000}]
   },
   {"id": 3,
    "steps": [
      {"name": "step1", "timeMs": 5000}, 
      {"name": "step2", "timeMs": 1000}, 
      {"name": "step3", "timeMs": 40000},
      {"name": "step4", "timeMs": 50000}]
   }
  ] 
}
```

# Output
You should produce a histogram of the execution time of each step, ordering the most expensive steps first. To aggregate each step, please use the _median_ execution time across all executions. 

Keep in mind:
* Histograms are meant to be readable. How will your histogram render a histogram where one step took 1 hour, the next step took 1 ms, and the next step took 3 minutes?
* The following enhancements are *not required*, but please structure your code assuming you might have to add them in the future:
  1. Ability to visualize other aggregate statistics easily (e.g. max execution time, average execution time)
  2. Error bars for the variability in runtime for a given step between executions 
  3. Ability to visualize a per-step histogram of execution, where the output is multiple charts, one per step, with a histogram of execution times. 


# Hand in your code
Please send your source code as well as a short paragraph description explaining the structure of your code and how your code could be modified to accommodate the extensions above.




