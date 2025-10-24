# Model Context Protocol (MCP) Configuration

This document outlines the MCP servers configured for this workspace and their usage.

## Configured Servers

### AWS Documentation Server
- **Server Name**: `aws-docs`
- **Package**: `awslabs.aws-documentation-mcp-server@latest`
- **Status**: Enabled
- **Purpose**: Provides access to AWS service documentation and best practices

### AWS Core Server
- **Server Name**: `aws-core`
- **Package**: `awslabs.core-mcp-server@latest`
- **Status**: Disabled (Package availability to be verified)
- **Purpose**: Core AWS services and foundational functionality

### AWS API Server
- **Server Name**: `aws-api`
- **Package**: `awslabs.aws-api-mcp-server@latest`
- **Status**: Enabled
- **Purpose**: Direct AWS API interactions and service management

### AWS Knowledge Server
- **Server Name**: `aws-knowledge-mcp-server`
- **URL**: `https://knowledge-mcp.global.api.aws`
- **Status**: Enabled
- **Purpose**: AWS architectural patterns, best practices, and knowledge base

### AWS CDK Server
- **Server Name**: `aws-cdk`
- **Package**: `awslabs.cdk-mcp-server@latest`
- **Status**: Enabled
- **Purpose**: AWS Cloud Development Kit (CDK) templates and constructs

### AWS Terraform Server
- **Server Name**: `aws-terraform`
- **Package**: `awslabs.terraform-mcp-server@latest`
- **Status**: Enabled
- **Purpose**: Terraform AWS provider resources and configurations

### AWS CloudFormation Server
- **Server Name**: `aws-cloudformation`
- **Package**: `awslabs.cloudformation-mcp-server@latest`
- **Status**: Enabled
- **Purpose**: CloudFormation templates and stack management

### AWS Serverless Server
- **Server Name**: `aws-serverless`
- **Package**: `awslabs.aws-serverless-mcp-server@latest`
- **Status**: Enabled
- **Purpose**: Serverless application patterns and SAM templates

### Fetch Server
- **Server Name**: `fetch`
- **Package**: `mcp-server-fetch`
- **Status**: Disabled
- **Purpose**: HTTP requests and web content fetching

## Available Tools by Server

### Documentation & Knowledge
- **aws-docs**: Search documentation, get service info, find best practices
- **aws-core**: Core AWS services, account management, foundational operations
- **aws-knowledge-mcp-server**: Access architectural patterns, design principles, well-architected framework

### Infrastructure as Code
- **aws-cdk**: Generate CDK constructs, stack templates, deployment patterns
- **aws-terraform**: Create Terraform configurations, resource definitions, modules
- **aws-cloudformation**: Build CloudFormation templates, nested stacks, parameters

### Serverless
- **aws-serverless**: SAM templates, serverless patterns, event-driven architectures

### API & Management
- **aws-api**: Direct AWS service calls, resource management, monitoring

## Usage Examples

### Documentation & Research
```bash
# Search AWS service documentation
# Get Lambda best practices
# Find security guidelines for S3
# Access Well-Architected Framework principles
```

### Infrastructure as Code
```bash
# Generate CDK stack for web application
# Create Terraform module for VPC
# Build CloudFormation template for RDS
# Design multi-tier architecture patterns
```

### Serverless Development
```bash
# Generate SAM template for API Gateway + Lambda
# Create Lambda function with event triggers
# Build serverless data processing pipeline
# Design event-driven architectures
```

### API Management
```bash
# List EC2 instances in region
# Create S3 bucket with versioning
# Configure CloudWatch alarms
# Manage IAM roles and policies
```

## Prerequisites

### Installation Requirements
The MCP servers use `uvx` to run, which requires `uv` (Python package manager):

```bash
# Install uv (choose one method)
# Via pip:
pip install uv

# Via homebrew (macOS):
brew install uv

# Or follow the official installation guide:
# https://docs.astral.sh/uv/getting-started/installation/
```

### Environment Setup
- **Documentation servers** (aws-docs, aws-knowledge): No AWS credentials required
- **Core server** (aws-core): May require AWS credentials for account operations
- **API server** (aws-api): Requires AWS credentials for service interactions
- **IaC servers** (aws-cdk, aws-terraform, aws-cloudformation): No credentials needed for template generation
- **Container servers** (aws-eks, aws-ecs): May require credentials for cluster management
- **Serverless servers** (aws-serverless, aws-lambda): May require credentials for deployment operations

### AWS Credentials Configuration
For servers requiring AWS access, configure credentials using:
```bash
# AWS CLI configuration
aws configure sso
```

## Configuration Management

### Enabling/Disabling Servers
To modify server status, edit `.kiro/settings/mcp.json`:
- Set `"disabled": false` to enable a server
- Set `"disabled": true` to disable a server

### Auto-Approval
Add tool names to the `autoApprove` array to automatically approve their usage:
```json
"autoApprove": ["search_aws_docs", "get_service_info"]
```

### Reconnection
- Servers reconnect automatically on config changes
- Manual reconnection available via MCP Server view in Kiro feature panel
- No Kiro restart required for configuration changes

## Troubleshooting

### Common Issues
1. **Server fails to start**: Ensure `uv` and `uvx` are installed
2. **Connection errors**: Check network connectivity
3. **Tool not found**: Verify server is enabled and connected
4. **Package not found**: Some AWS MCP server packages may not be available yet (e.g., aws-core)

### Logs
- Set `FASTMCP_LOG_LEVEL` environment variable for debugging
- Available levels: `DEBUG`, `INFO`, `WARNING`, `ERROR`

## Best Practices

### Server Usage Strategy
- **Documentation & Knowledge**: Start here for research and architectural guidance
- **Core Server**: Use for foundational AWS operations and account management
- **IaC Servers**: Use for generating infrastructure templates and configurations
- **Serverless Server**: Ideal for event-driven and serverless architectures
- **API Server**: Use for direct AWS resource management and monitoring

### Development Workflow
1. **Research**: Use aws-docs and aws-knowledge for best practices
2. **Design**: Generate IaC templates with CDK, Terraform, or CloudFormation servers
3. **Implement**: Use serverless server for application deployment
4. **Manage**: Leverage aws-api for ongoing resource management

### Security Considerations
- Only enable servers you actively use to minimize attack surface
- Use auto-approval carefully - only for trusted, well-understood tools
- Regularly review and rotate AWS credentials used by API-enabled servers
- Monitor server logs for unusual activity

### Performance Optimization
- Keep frequently used servers enabled
- Disable unused servers to reduce resource usage
- Group related servers by project phase (research, development, deployment)
- Use specific server tools rather than generic queries for better performance

### Troubleshooting Tips
- Start with documentation servers for understanding service capabilities
- Use knowledge server for architectural patterns and best practices
- Leverage multiple IaC servers to compare different approaches
- Test configurations locally before deploying through API server