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
  samples=("sample1" "sample2" "sample3" "sample4" "sample5")

  for sample in "${samples[@]}"; do
      echo "Processing $sample for genetic analysis"
  done
  ```
  
  </details>

#### 3. Write a script that monitors a patient's blood pressure readings for 3 consecutive checks using a while loop. Initialize blood pressure at 140 and decrease it by 5 for each check. Print "BP Check [number]: [value]".

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash
  bp=140
  check=1

  while [ $check -le 3 ]; do
      echo "BP Check $check: $bp"
      bp=$((bp - 5))
      check=$((check + 1))
  done
  ```
  
  </details>

#### 4. Create a script that processes patient samples. Each time it processess a patient, it will print out processing patient sample number every 2 seconds. Use a combination of for loop and sleep command. Process a total of 9 samples. 

  <details>
  <summary>Click to view answer</summary>

  ```
 #!/bin/bash

  total_samples=9

  for ((i=1; i<=$total_samples; i++)); do
      echo "Processing patient sample number $i"
      sleep 1  # Simulate processing time of 1 second
  done

  echo "All $total_samples samples have been processed"
  ```
  
  </details>

#### 5. Write a script that categorizes genetic variants based on their frequency in a population. Ask the user for the frequency of the genetic variant. Categorize them as: Common (>5%), Low frequency (1-5%), or Rare (<1%).

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash

  # Prompt user for the variant frequency
  echo "Please enter the genetic variant frequency:"
  read frequency

  if ((frequency_percent > 5)); then
      echo "This is a Common variant (frequency > 5%)"
  elif ((frequency_percent >= 1 && frequency_percent <= 5)); then
      echo "This is a Low frequency variant (1% <= frequency <= 5%)"
  else
      echo "This is a Rare variant (frequency < 1%)"
      echo "Frequency provided: $frequency_percent%"
  fi
  ```
  
  </details>
