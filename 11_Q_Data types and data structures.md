## Basic questions

#### 1. Create a simple array of 5 patient IDs (as strings) and display the total number of patients. Then access and display the ID of the third patient. The patient IDs are PT001, PT002, PT003, PT004 and PT005.

  <details>
  <summary>Click to view answer</summary>

  ```
#!/bin/bash

# Answer:
patient_ids=("PT001" "PT002" "PT003" "PT004" "PT005")
echo "Total patients: ${#patient_ids[@]}"
echo "Third patient ID: ${patient_ids[2]}"
  ```
  
  </details>
