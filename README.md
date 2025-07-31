# GitHub Copilot Prompts for Azure MCP Server

This repository contains specialized GitHub Copilot prompt files designed to work with the Azure MCP (Model Context Protocol) Server, providing intelligent assistance for Azure infrastructure development, particularly focusing on Bicep module analysis and Azure best practices.

## What Are GitHub Copilot Prompts?

GitHub Copilot prompts are structured instructions that help guide AI models to provide more accurate, contextual, and specialized assistance. When integrated with the Azure MCP Server, these prompts enable Copilot to:

- Access real-time Azure resource information
- Understand Azure-specific contexts and best practices
- Provide intelligent suggestions for infrastructure as code
- Analyze and review Bicep modules against Azure standards
- Offer recommendations for security, scalability, and cost optimization

## How Prompts Are Used

GitHub Copilot prompts serve as specialized AI agents that:

1. **Define Context**: Establish the role and expertise level (e.g., "Cloud Solution Architect")
2. **Set Tools**: Specify which tools and services the AI can access (Azure MCP Server, codebase analysis, search)
3. **Provide Instructions**: Give detailed guidance on how to analyze and respond to user queries
4. **Establish Standards**: Define evaluation criteria and best practices to follow

When you use a prompt, it transforms your GitHub Copilot experience by providing:
- Domain-specific expertise in Azure architecture
- Consistent evaluation criteria across projects
- Access to real-time Azure data through MCP integration
- Structured analysis and recommendations

## Creating New Prompt Files in VSCode

To create a new GitHub Copilot prompt file in Visual Studio Code:

### Step 1: Access the Chat New Prompt File Feature
1. Open Visual Studio Code
2. Access the Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P`)
3. Type "Chat: New Prompt File" and select it
4. Alternatively, you can use the GitHub Copilot Chat panel and look for the "New Prompt" option

### Step 2: Create Your Prompt File
1. VS Code will create a new `.prompt.md` file
2. The file will include basic front matter structure:
   ```markdown
   ---
   mode: agent
   tools: []
   ---
   ```

### Step 3: Configure Your Prompt
1. **Mode**: Set to `agent` for specialized AI behavior
2. **Tools**: Add tools like `['codebase', 'Azure MCP Server', 'search']`
3. **Content**: Write your prompt instructions below the front matter

### Example Structure:
```markdown
---
mode: agent
tools: ['codebase', 'Azure MCP Server', 'search']
---
You are a [ROLE] agent. Your task is to [SPECIFIC_TASK].

- Use the Azure MCP Server to [SPECIFIC_ACTIONS]
- Focus on [SPECIFIC_AREAS]
- Provide [SPECIFIC_OUTPUT_FORMAT]
```

## Prompt Engineering Best Practices

### 1. Clear Role Definition
- Define a specific, expert role (e.g., "Cloud Solution Architect", "DevOps Engineer")
- Specify the level of expertise and perspective
- Set the context for the type of work being performed

### 2. Specific Tool Integration
- Always include relevant tools in the front matter
- For Azure work, include 'Azure MCP Server' to enable real-time Azure data access
- Include 'codebase' for repository analysis capabilities
- Add 'search' for broader information gathering

### 3. Structured Instructions
- Break down complex tasks into clear, numbered steps
- Use bullet points for lists of requirements or criteria
- Provide specific examples of expected behavior

### 4. Evaluation Criteria
- Define clear metrics for assessment (e.g., 1-10 scoring scales)
- Specify the areas of focus (security, performance, cost, etc.)
- Include both qualitative and quantitative measures

### 5. Interactive Elements
- Encourage the AI to ask clarifying questions
- Specify when user input is needed
- Define how the AI should handle ambiguous scenarios

### 6. Output Format Specification
- Clearly define the expected structure of responses
- Specify formatting requirements (markdown, sections, etc.)
- Include templates or examples when helpful

## Example Output from Bicep Review Prompt

When using the `bicep-review.prompt.md` included in this repository, you can expect output like:

### Sample Analysis Report

```markdown
## Bicep Module Analysis Report

### Module: Storage Account with Private Endpoint
**Repository**: /modules/storage/storage-account-private

#### Overall Assessment
This module creates an Azure Storage Account with private endpoint connectivity, following most Azure best practices with some areas for improvement.

#### Detailed Scoring

**Security: 8/10**
- ✅ Private endpoint implementation prevents public access
- ✅ RBAC assignments properly configured
- ⚠️ Missing: Customer-managed encryption keys option
- ⚠️ Missing: Network access restrictions configuration

**Scalability: 7/10**
- ✅ Supports multiple storage tiers
- ✅ Parameterized sizing options
- ⚠️ Missing: Auto-scaling policies for blob storage

**Maintainability: 9/10**
- ✅ Well-documented parameters and outputs
- ✅ Consistent naming conventions
- ✅ Modular design with clear separation of concerns

**Performance: 8/10**
- ✅ Appropriate storage tier selection
- ✅ Optimized for regional deployment
- ⚠️ Consider: Premium tier options for high-performance scenarios

**Cost Optimization: 6/10**
- ⚠️ Missing: Lifecycle management policies
- ⚠️ Missing: Storage tier optimization guidance
- ✅ Appropriate default sizes

#### Recommendations
1. Implement lifecycle management policies to automatically tier data
2. Add customer-managed encryption key support
3. Include cost estimation parameters
4. Add monitoring and alerting configurations
```

## Azure MCP Server Integration

This repository is specifically designed to work with the Azure MCP Server, which provides:

### Real-time Azure Data Access
- Current subscription information
- Resource group details
- Existing resource configurations
- Pricing and cost information
- Compliance and security status

### Enhanced Analysis Capabilities
- Cross-reference with existing Azure resources
- Validate against current Azure policies
- Check for naming convention compliance
- Assess regional availability and constraints

### Integration Benefits
- **Contextual Awareness**: Prompts can understand your current Azure environment
- **Real-time Validation**: Check configurations against live Azure data
- **Cost Analysis**: Access current pricing for accurate cost projections
- **Compliance Checking**: Validate against organizational policies and Azure standards

## Customizable Agent Roles

The prompt system supports various agent roles that can be customized based on your needs:

### Available Roles:
- **Cloud Solution Architect**: Focuses on high-level design and best practices
- **DevOps Engineer**: Emphasizes automation, CI/CD, and operational efficiency
- **Security Architect**: Prioritizes security configurations and compliance
- **Cost Optimization Specialist**: Focuses on cost-effective resource utilization
- **Platform Engineer**: Concentrates on platform reliability and scalability

### Customizing Agent Roles:
To change the agent role, modify the prompt description:

```markdown
You are a "[NEW_ROLE]" agent. Your expertise includes [SPECIFIC_SKILLS].
Focus your analysis on [ROLE_SPECIFIC_PRIORITIES].
```

### Role-Specific Benefits:
- **Tailored Responses**: Each role provides perspective relevant to that discipline
- **Specialized Vocabulary**: Uses terminology appropriate for the target audience
- **Focused Analysis**: Emphasizes aspects most relevant to the role
- **Contextual Recommendations**: Provides advice aligned with role responsibilities

## Model Recommendations for Bicep Module Review

Based on community feedback and testing, here are recommended AI models for different aspects of Bicep module evaluation:

### Primary Recommendations:

#### **Claude 3.5 Sonnet** (Highly Recommended)
- **Strengths**: Excellent at code analysis, Azure best practices understanding
- **Best For**: Comprehensive module reviews, security analysis, architectural recommendations
- **Why**: Strong reasoning capabilities and detailed explanations

#### **GPT-4 Turbo**
- **Strengths**: Good Azure knowledge, strong at pattern recognition
- **Best For**: Code optimization suggestions, performance analysis
- **Why**: Extensive training on Azure documentation and patterns

#### **GPT-4o**
- **Strengths**: Fast response times, good for iterative development
- **Best For**: Quick reviews, syntax checking, basic best practice validation
- **Why**: Balanced performance and speed for development workflows

### Specialized Use Cases:

#### **For Security-Focused Reviews**:
- **Claude 3.5 Sonnet**: Superior at identifying security misconfigurations
- **GPT-4**: Good at compliance checking and policy validation

#### **For Cost Optimization**:
- **Claude 3.5 Sonnet**: Excellent at analyzing resource sizing and cost implications
- **GPT-4 Turbo**: Good at suggesting cost-effective alternatives

#### **For Large-Scale Analysis**:
- **GPT-4o**: Faster processing for bulk module reviews
- **Claude 3.5 Sonnet**: More thorough analysis when speed is less critical

### Community Recommendations:
We encourage users to share their experiences with different models:
- Create issues to report model performance observations
- Share specific use cases where certain models excel
- Contribute examples of particularly effective model + prompt combinations

## Additional Important Considerations

### Version Control Best Practices
- Store prompts in version control alongside your infrastructure code
- Use descriptive commit messages when updating prompts
- Tag stable versions of prompts for consistent team usage

### Team Collaboration
- Establish team standards for prompt usage
- Share effective prompts across team members
- Document custom modifications and their purposes

### Continuous Improvement
- Regularly review and update prompts based on new Azure features
- Gather feedback from team members on prompt effectiveness
- Monitor Azure best practice updates and incorporate them into prompts

### Integration with Development Workflow
- Use prompts during code reviews for consistent evaluation
- Integrate with CI/CD pipelines for automated analysis
- Combine with other Azure tools like Azure Policy and Advisor

### Privacy and Security
- Be mindful of sensitive information when using prompts
- Ensure prompts don't expose confidential configuration details
- Follow your organization's guidelines for AI tool usage

## Getting Started

1. **Clone this repository** to access the existing prompts
2. **Install the Azure MCP Server** for full functionality
3. **Configure GitHub Copilot** in your development environment
4. **Import the prompt files** into your VSCode workspace
5. **Start using prompts** for your Bicep module development and review

## Contributing

We welcome contributions to improve these prompts:
- Submit issues for bugs or enhancement requests
- Create pull requests with improved prompt versions
- Share your custom prompts that others might find useful
- Report your experiences with different AI models

---

**Note**: This repository is designed to work optimally with the Azure MCP Server. While prompts can function without it, the full capabilities and real-time Azure integration require the MCP server to be properly configured.