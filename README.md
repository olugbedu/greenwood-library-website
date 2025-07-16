# Error Handling in Shell Scripting

Error handling is a critical component in creating robust and reliable shell scripts. This project demonstrates how to anticipate, detect, and handle errors effectively, especially when dealing with cloud resources like AWS S3.

---

## Steps Taken to Complete the Task

### 1. **Identifying Potential Errors**

I began by identifying areas where errors are likely to occur:
- **File existence checks**
- **Command execution failures**
- **Invalid user inputs**
- **AWS CLI operations (e.g., creating an S3 bucket)**

### 2. **Implementing Conditional Logic**

I used `if`, `elif`, and `else` statements to validate conditions and handle different scenarios. Specifically, I used the exit status `$?` of commands to determine whether they succeeded or failed:
- `0` means success
- Any non-zero value indicates an error

### 3. **Providing Informative Messages**

Clear error messages were added to ensure users are aware of what went wrong and how to address it.

Example snippet used:
```bash
if [ ! -f "$file" ]; then
    echo "Error: File $file not found. Please verify the path."
    exit 1
fi
```

---

## S3 Bucket Existence Check Example

### Objective:
Prevent redundant AWS S3 bucket creation by checking if a bucket already exists.

### Script:
```bash
create_s3_bucket() {
    local bucket_name="gbedu-bucket"

    # Check if bucket exists
    if aws s3api head-bucket --bucket "$bucket_name" 2>/dev/null; then
        echo "S3 bucket '$bucket_name' already exists."
    else
        # Create bucket if it doesn't exist
        if aws s3 mb "s3://$bucket_name" --region us-east-1; then
            echo "S3 bucket '$bucket_name' created successfully."
        else
            echo "Error: Failed to create S3 bucket '$bucket_name'."
            exit 1
        fi
    fi
}
```

---

## Key Improvements in the Script

| Feature        | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| **Prevention** | Prevents duplicate creation of existing S3 buckets using `head-bucket`.     |
| **Clarity**    | Provides success/failure messages after each action.                        |
| **Termination**| Script exits gracefully on failure to avoid further errors.                 |

---

## Summary of the Task

This task involved enhancing the reliability of a shell script by:
- Validating the existence of AWS resources before taking action.
- Using conditional logic to branch based on command results.
- Displaying meaningful output to inform users of script status.
- Preventing unnecessary AWS operations, saving time and cost.

---

## Key Commands Used

| Command                  | Purpose                                         |
|--------------------------|-------------------------------------------------|
| `aws s3api head-bucket`  | Check if an S3 bucket exists                    |
| `aws s3 mb`              | Create a new S3 bucket                          |
| `2>/dev/null`            | Suppress error output from a command            |
| `exit 1`                 | Terminate script execution on failure           |

---

## Lessons Learned

- Use `if` statements and exit codes to control the flow of execution.
- Always verify external dependencies (like cloud resources) before acting on them.
- Comment your scripts to improve maintainability and readability.
