## Test Results

### How to view JMeter Results
  * Clone hydranorth-load-testing project
  ```
  git clone git@github.com:ualbertalib/hydranorth-load-testing.git
  ```
  * Start JMeter
  * Open [load testing plan](https://github.com/ualbertalib/hydranorth-load-testing/blob/master/apache-jmeter/plan/hn-test-plan.jmx)
  * Expand thread group node
  * Click on result listener (Ex: Graph Results)
  * Click browse button and open result file

### 2015.05.13: Test Results for Upload 10 Users 1 Loop
* Server: oldham.library.ualberta.ca

Samples | Failed  | Max (ms) | Min (ms) | Ave (ms) | Throuhput (#/m) | KB/s
------------------- | -------- | ------------ | ----------- | ------------ | --------------------- | --------
23 | 1 | 114578 | 7920 | 33650 | 1.8 | 0.04

JMeter Results: [2015.05.13 - Upload 10 Users 1 Loop](https://github.com/ualbertalib/hydranorth-load-testing/tree/master/apache-jmeter/test-results/2015.05.13%20-%20Upload%2010%20Users%201%20Loop)

### 2015.05.13: Test Results for Upload 10 Users 5 Loops
* Server: oldham.library.ualberta.ca
* Average File Size: 56 KB
* Time Start/End: 14:50/18:12
* Total Time: 3 h 22 m

Samples | Failed  | Max (ms) | Min (ms) | Ave (ms) | Throuhput (#/m) | KB/s
------------------- | -------- | ------------ | ----------- | ------------ | --------------------- | --------
1150| 183 | 358424 | 14 | 102583 | 5.7 | 0.08

*All failed are internal server error because of not enough space on tmp directory.

JMeter Results: [2015.05.13 - Upload 10 Users 5 Loops](https://github.com/ualbertalib/hydranorth-load-testing/tree/master/apache-jmeter/test-results/2015.05.13%20-%20Upload%2010%20Users%201%20Loop)
