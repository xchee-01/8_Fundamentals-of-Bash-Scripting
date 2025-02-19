## Basic questions 

#### 1. Write a bash script that checks if a patient's creatinine level is above the normal range (>1.2 mg/dL). The script should output "High creatinine level - Further investigation needed" if above 1.2, and "Normal creatinine level" if below or equal to 1.2.

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash
  creatinine=1.4

  if [ $(echo "$creatinine > 1.2" | bc) -eq 1 ]; then
      echo "High creatinine level - Further investigation needed"
  else
      echo "Normal creatinine level"
  fi  
  ```
  
  </details>

#### 2. Create a script that processes a list of 5 DNA samples (sample1 through sample5) using a for loop. For each sample, it should print "Processing [sample_name] for genetic analysis".
  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash
  creatinine=1.4

  if [ $(echo "$creatinine > 1.2" | bc) -eq 1 ]; then
      echo "High creatinine level - Further investigation needed"
  else
      echo "Normal creatinine level"
  fi  
  ```
  
  </details>
