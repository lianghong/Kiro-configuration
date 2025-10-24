---
title: Bash Best Practices
inclusion: fileMatch
fileMatchPattern: '*.sh'
---

# Bash Best Practices

## Code Style
- Use `#!/bin/bash` shebang for bash-specific features
- Use meaningful variable and function names
- Use lowercase with underscores for variables and functions
- Use UPPERCASE for environment variables and constants
- Indent with 2 spaces consistently
- Keep lines under 80 characters when possible

## Variable Handling
- Quote variables to prevent word splitting: `"$variable"`
- Use `${variable}` for clarity in complex expressions
- Use `readonly` for constants
- Use `local` for function variables
- Check if variables are set: `${variable:-default}`
- Use arrays for lists: `array=("item1" "item2")`

## Error Handling
- Use `set -e` to exit on any command failure
- Use `set -u` to exit on undefined variables
- Use `set -o pipefail` to catch pipeline failures
- Check command exit codes explicitly when needed
- Use `trap` for cleanup on script exit
- Validate input parameters and file existence

## Code Organization
- Use functions for reusable code blocks
- Keep main logic at the bottom of the script
- Source external scripts with `. script.sh` or `source script.sh`
- Use meaningful file names with `.sh` extension
- Organize related scripts in directories
- Use configuration files for settings

## Testing
- Test scripts with `bash -n script.sh` for syntax
- Use `shellcheck` for static analysis
- Test with different input scenarios
- Use `set -x` for debugging output
- Test on target environments
- Run with minimal output: redirect stderr `2>/dev/null`
- Test specific functions: `bash -c "source script.sh; test_function"`

## Performance
- Use built-in commands over external tools when possible
- Avoid unnecessary subshells and command substitutions
- Use `[[ ]]` instead of `[ ]` for conditionals
- Use parameter expansion instead of `sed`/`awk` for simple operations
- Cache expensive operations in variables
- Use `printf` instead of `echo` for portability
