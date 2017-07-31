# interview-backend-histogram
Write a histogram builder!

# Overview
In order to identify threats for our customers, LogicHub analyzes customer data in a number of steps. You will write an application to visualize execution time statistics about each step.

You will write the following application: 

```
./histogram.sh PATH_TO_JSON 
```

- The application is initialized with a path to a JSON file with runtime statistics for each step
- Your application should output a histogram with aggregate statistics about each step:

```
step3: (30s) ############################## 
step4: (10s) ##########
step1: (5s)  #####
step2: (1s)  #

```

# Input format
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
