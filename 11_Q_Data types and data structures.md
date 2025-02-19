## Basic questions

#### 1. Create a simple array of 5 patient IDs (as strings) and display the total number of patients. Then access and display the ID of the third patient. The patient IDs are PT001, PT002, PT003, PT004 and PT005.

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash

  patient_ids=("PT001" "PT002" "PT003" "PT004" "PT005")
  echo "Total patients: ${#patient_ids[@]}"
  echo "Third patient ID: ${patient_ids[2]}"
  ```
  
  </details>

#### 2. Create a script that processes a list of drug dosages (floating point numbers) and calculates their sum. Use basic arithmetic operations.

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash

  dosages=(2.5 3.0 2.75 3.25 2.0)
  sum=0
  for dosage in "${dosages[@]}"
  do
      sum=$(echo "$sum + $dosage" | bc)    #remember that bc is a different way of doing calculations
  done
  echo "Total dosage: $sum mg"
  ```
  
  </details>

#### 3. Write a script that takes a patient's age as input and determines if they are eligible for a clinical trial (age > 18 and age < 65).

  <details>
  <summary>Click to view answer</summary>

  ```
  #!/bin/bash

  echo "Enter patient age:"
  read age

  if [ $age -gt 18 ] && [ $age -lt 65 ]; then
      echo "Patient is eligible for clinical trial"
  else
      echo "Patient is not eligible for clinical trial"
  fi
  ```
  
  </details>

#### 4. Create a script that stores mutation status (true/false) for 5 patients in an array and counts how many patients have mutations.

> [!TIP]
> You will need the code `((count++))`
>
> You can read more [here](https://linuxize.com/post/bash-increment-decrement-variable/)

  ```
  #!/bin/bash

  mutation_status=(true false true true false)
  count=0

  for status in "${mutation_status[@]}"
  do
      if [ "$status" = true ]; then
          ((count++))
      fi
  done

  echo "Number of patients with mutations: $count"
  ```

#### 5. Write a script that maintains an array of gene names and allows adding new genes to the array. Display the updated array after each addition and count how many genes in the new gene list. 

  ```
  #!/bin/bash

  genes=("BRCA1" "TP53" "EGFR")
  echo "Current genes: ${genes[@]}"

  echo "Enter new gene name:"
  read new_gene
  genes+=("$new_gene")

  echo "Updated gene list: ${genes[@]}"
  echo "Total number of genes: ${#genes[@]}"
  ```
