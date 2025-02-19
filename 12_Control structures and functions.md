# 8. Control structures and functions

Control structures and functions form the backbone of shell scripting, enabling you to create sophisticated and reliable programs for medical data analysis and genomic processing. Think of control structures as the decision-making and repetitive task handlers in your scripts, while functions are reusable blocks of code that can be called whenever needed.

## 8.1. Conditional statements 

Just a recap of what conditional statements are: 

**If-then** statements are like medical decision trees: if a condition is true, do something
**Elif** (else-if) allows for multiple conditions, like different treatment paths based on test results
**Else** provides a default action when no conditions are met

### 8.1.1. If statements

If statements help your script make decisions based on conditions. 

For example,

```
#!/bin/bash
# save as check_temperature.sh

# Simple medical example
temperature=38.5

if [ "$temperature" -gt 37.5 ]; then
    echo "Patient has fever"
else
    echo "Temperature is normal"
fi
```

> [!NOTE]
> To run this code, you can either do `bash check_temperature.sh`
>
> or
>
> ```
> chmod +x check_temperature.sh
> ./check_temperature.sh
> ```

### 8.1.2. For Loops

For loops help you do the same task multiple times, like processing multiple patient files or running the same analysis on different samples.

For example,

```
#!/bin/bash
# save as process_samples.sh

# Simple genomics example
samples=("sample1" "sample2" "sample3")

for sample in "${samples[@]}"; do
    echo "Processing $sample..."
done
```

### 8.1.3. While Loops

While loops keep doing something as long as a condition is true. 

For example, 

```
#!/bin/bash
# save as monitor_patient.sh

# Simple monitoring example
count=1
while [ $count -le 3 ]; do
    echo "Checking patient vitals - Hour $count"
    count=$((count + 1))
done
```

### 8.1.4. Case statements

Case statements are like multiple-choice questions - they help you handle different scenarios based on a specific value.

For example, 

```
#!/bin/bash
# save as check_status.sh

# Simple medical status example
status="critical"

case $status in
    "normal")
        echo "Continue regular monitoring"
        ;;                                     # End of this case
    "warning")
        echo "Increase monitoring frequency"
        ;;                                     # End of this case
    "critical")  
        echo "Alert medical team"
        ;;                                     # End of this case
    *)
        echo "Unknown status"
        ;;                                     # End of this case
esac                                           # End of case statement (case spelled backwards)
```
