# Working with Functions in Shell Scripting

## Project Overview

This mini-project focuses on the use of **functions in shell scripting**, aiming to help DataWise Solutions automate infrastructure setup processes, particularly for **AWS EC2 instances** and **S3 buckets**. Functions improve script structure, make code reusable, and allow logical segregation of tasks.

---

## Task Execution Steps

### 1. Defined Environment Variable

The script starts by accepting an environment as an argument:
```bash
ENVIRONMENT=$1
```

This variable determines whether the script is being executed for the `local`, `testing`, or `production` environment.

---

### 2. Implemented `check_num_of_args` Function

This function ensures that the script receives exactly one argument:
```bash
check_num_of_args() {
    if [ "$#" -ne 1 ]; then
        echo "Usage: $0 <environment>"
        exit 1
    fi
}
```
 **Purpose**: Prevents the script from executing without the required environment parameter.

---

### 3. Added AWS CLI Check with `check_aws_cli` Function

```bash
check_aws_cli() {
    if ! command -v aws &> /dev/null; then
        echo "AWS CLI is not installed. Please install it before proceeding."
        return 1
    fi
}
```
 **Purpose**: Ensures the `aws` command-line tool is installed before executing AWS-related commands.

---

### 4. Verified AWS Profile Using `check_aws_profile`

```bash
check_aws_profile() {
    if [ -z "$AWS_PROFILE" ]; then
        echo "AWS profile environment variable is not set."
        return 1
    fi
}
```
 **Purpose**: Checks whether an AWS profile is configured using the `$AWS_PROFILE` environment variable.

---

### 5. Introduced `activate_infra_environment` Placeholder

This is a stub for future infrastructure-specific logic:
```bash
activate_infra_environment() {
    # Implementation for activating infrastructure environment
}
```

---

### 6. Environment Routing Logic

After all pre-checks, the script determines the infrastructure environment:
```bash
if [ "$ENVIRONMENT" == "local" ]; then
    echo "Running script for local Environment..."
elif [ "$ENVIRONMENT" == "testing" ]; then
    echo "Running script for Testing Environment..."
elif [ "$ENVIRONMENT" == "production" ]; then
    echo "Running script for Production Environment..."
else
    echo "Invalid environment specified. Please use 'local', 'testing', or 'production'."
    exit 2
fi
```

---

### 7. Final Script Structure

```bash
#!/bin/bash

ENVIRONMENT=$1

check_num_of_args() {
    if [ "$#" -ne 1 ]; then
        echo "Usage: $0 <environment>"
        exit 1
    fi
}

activate_infra_environment() {
    # Future implementation for activating environment
}

check_aws_cli() {
    if ! command -v aws &> /dev/null; then
        echo "AWS CLI is not installed. Please install it before proceeding."
        return 1
    fi
}

check_aws_profile() {
    if [ -z "$AWS_PROFILE" ]; then
        echo "AWS profile environment variable is not set."
        return 1
    fi
}

# Function calls
check_num_of_args
activate_infra_environment
check_aws_cli
check_aws_profile

# Environment decision
if [ "$ENVIRONMENT" == "local" ]; then
    echo "Running script for local Environment..."
elif [ "$ENVIRONMENT" == "testing" ]; then
    echo "Running script for Testing Environment..."
elif [ "$ENVIRONMENT" == "production" ]; then
    echo "Running script for Production Environment..."
else
    echo "Invalid environment specified. Please use 'local', 'testing', or 'production'."
    exit 2
fi
```

---

## Key Learnings

- **Encapsulation with functions** helps modularize and maintain scripts.
- **Environment-based scripting** allows flexibility across multiple deployment stages.
- **Pre-checks like CLI installation and environment variables** reduce runtime failures.
- **Clear function names and structure** increase readability and maintainability.

---

## Final Thoughts

This project deepened my understanding of shell scripting best practices. By building reusable functions for argument validation, AWS CLI checks, and environment profile validation, I created a script that is clean, efficient, and production-ready. These concepts are foundational for building more complex infrastructure-as-code scripts and serve as a solid base for further automation in DevOps workflows.
