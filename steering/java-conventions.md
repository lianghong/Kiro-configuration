```
 File              : java-conventions.md
 Author            : Lianghong Fei <feilianghong@gmail.com>
 Date              : 2025-10-22
 Last Modified Date: 2025-10-22
 Last Modified By  : Lianghong Fei <feilianghong@gmail.com>
```
# Java Project Conventions

## Architecture Patterns
- Use hexagonal architecture for complex domains
- Implement CQRS for read/write separation when needed
- Apply Domain-Driven Design principles for business logic

## Testing Strategy
- Write unit tests for all business logic
- Use TestContainers for integration tests
- Maintain 80% code coverage minimum
- Follow the AAA pattern (Arrange, Act, Assert)

## Error Handling
- Use custom exceptions for business logic errors
- Implement global exception handlers with @ControllerAdvice
- Log errors with correlation IDs for traceability
- Return consistent error response formats

## Performance Guidelines
- Use connection pooling for database access
- Implement caching strategies for frequently accessed data
- Use async processing for long-running operations
- Monitor and optimize database queries
