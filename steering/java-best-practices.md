---
title: Java Best Practices
inclusion: fileMatch
fileMatchPattern: '*.java'
---

# Java Best Practices

## Code Style
- Follow Oracle Java Code Conventions
- Use meaningful variable and method names
- Use camelCase for variables and methods
- Use PascalCase for classes and interfaces
- Use UPPER_SNAKE_CASE for constants
- Limit line length to 120 characters
- Use proper indentation (4 spaces)

## Type Safety
- Use generics to ensure type safety
- Prefer `var` for local variables when type is obvious (Java 10+)
- Use `Optional` for nullable return values
- Avoid raw types and unchecked casts
- Use sealed classes for restricted inheritance (Java 17+)

## Error Handling
- Use specific exception types
- Handle exceptions at appropriate levels
- Use try-with-resources for resource management
- Log errors with appropriate detail using SLF4J
- Prefer unchecked exceptions for programming errors

## Code Organization
- Use Maven or Gradle for dependency management
- Follow standard package naming conventions (reverse domain)
- Organize code into logical packages
- Use proper access modifiers (private, protected, public)
- Prefer composition over inheritance

## Testing
- Write unit tests using JUnit 5
- Use descriptive test method names
- Mock dependencies with Mockito
- Aim for high test coverage
- Use `@BeforeEach` and `@AfterEach` for setup/cleanup
- Run tests with minimal output: `mvn test -q` or `gradle test --console=plain`
- Filter specific tests: `mvn test -Dtest="TestClassName#testMethod"`

## Performance
- Use StringBuilder for string concatenation in loops
- Use appropriate collection types (ArrayList, HashMap, etc.)
- Profile code before optimizing with JProfiler or similar tools
- Use streams judiciously (Java 8+)
- Consider record classes for immutable data (Java 14+)
- Use text blocks for multi-line strings (Java 15+)
