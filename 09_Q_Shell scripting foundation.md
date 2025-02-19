## Basic questions

#### 1. What is the purpose of the shebang line in a shell script and where should it be placed? 

  <details>
  <summary>Click to view answer</summary>

  ```
  The shebang line tells the system which interpreter should be used to   execute the script (in this case, Bash). It must always be placed on the very first line of the script. Without it, you would need to explicitly type bash script.sh to run the script.
  ```
  
  </details>

#### 2. Write a basic shell script that declares a variable patient_sample with the value "BRCA1_mut" and prints it.

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash
  patient_sample="BRCA1_mut"
  echo $patient_sample
  ```
  
  </details>

#### 3. How would you modify the following script to accept user input for a patient ID and store it in a file called patient_records.txt?

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash
  read -p "Enter patient ID: " patient_id
  echo "Patient ID: $patient_id" >> patient_records.txt
  ```
  
  </details>

#### 4. Create a shell script that stores three vital signs (temperature, heart rate, and blood pressure) in an array and prints each value. 

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash
  vitals=(98.6 72 "120/80")
  echo "Temperature: ${vitals[0]}"
  echo "Heart Rate: ${vitals[1]}"
  echo "Blood Pressure: ${vitals[2]}"
  ```
  
  </details>

#### 5. Write a script that calculates the expression levels from three RNQseq sequencing runs using bash arithmetic. The expression levels are 1000000, 1500000 and 1200000.

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash
  run1_reads=1000000
  run2_reads=1500000
  run3_reads=1200000

  ((total_reads = run1_reads + run2_reads + run3_reads))
  echo "Total sequencing reads: $total_reads"
  ```
  
  </details>

#### 6. Write a script that asks users how much storage space is needed in GB. If the space needed exceeds 3GB, tells the user that there is not enough space in the computer. 

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash

  read -p "How much storage space do you need (in GB)? " space_needed

  # Check if space needed exceeds 3GB
  if ((space_needed > 3)); then
      echo "Error: Not enough space available. Maximum space is 3GB."
  else
      echo "Space requirement acceptable."
  fi
  ```
  
  </details>

#### 7. Write a shell script that calculates the molarity (M) of a solution by accepting user inputs for volume (in cm³), mass (in grams), and molecular weight (in g/mol). The script will then output the results and display the results in millimolar (mM).

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash

  # Get user inputs
  read -p "Enter volume (in cm³): " volume_cm3
  read -p "Enter mass (in grams): " mass
  read -p "Enter molecular weight (in g/mol): " mol_weight

  # Calculate molarity
  ((molarity_mM = (mass * 1000000) / (mol_weight * volume_cm3)))

  echo "Concentration: $molarity_mM mM"
  ```
  
  </details>
