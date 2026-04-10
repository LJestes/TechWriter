# Getting Started with AWS Accounts

## [Acquiring an AWS Account](https://github.com/hpe-sre/platform-doc-portal/blob/main/docs/accts-subscrips/aws/account-requests.md)
- Details the self-service process for requesting AWS accounts through GitHub pull requests
- Covers supported Master Payer Accounts (MPAs) for all BUs.
  - See also [Additional AWS and MPA information](#additional-aws-and-mpa-information)
- Provides YAML template for account creation with required fields including environment, service details, organizational unit, user permissions, GitHub teams, HPE metadata, and PagerDuty configuration
- Process involves forking the account-create-requests repo, filling out templates, and getting FinOps and CyberSec approval
- Automated Jira ticket creation tracks remaining CCP team work

After creating the account yaml, you receive your account email from a CCP team member with the account information, as well as all related repositories.

### Additional AWS and MPA information
#### [Understanding the Master Payer Account Architecture](https://github.com/hpe-sre/platform-doc-portal/blob/main/docs/accts-subscrips/aws/mgm-acct-lifecycle.md)

- Explains the repository structure for managing MPA resources
- Details three key repositories:
  - aws-$MPA-master-payer-config: Core MPA configuration with restricted access
  - aws-$MPA-organization-config: AWS Organizations management via YAML inputs
  - aws-$MPA-account-config: Sub-account boilerplate management
- Covers delegated management accounts for AWS IAM Identity Center, SecOps, and central logging

#### [Working with the Master Payer Account (MPA) Admin](https://github.com/hpe-sre/platform-doc-portal/blob/main/docs/accts-subscrips/aws/mpa-admin.md)

- Defines administrator roles and responsibilities for MPA management
- Covers root user capabilities and best practices including centralized root access management
- Details IAM administrator role responsibilities: account management, billing, and security policies
- Explains OrganizationAccountAccessRole usage and best practices
- Outlines expectations including Terraform plan understanding, password rotation, and careful SCP changes
- Provides access acquisition procedures and production access request processes


## [After receiving your account](https://github.com/hpe-sre/platform-doc-portal/blob/main/docs/accts-subscrips/aws/acct-complete.md)
- Post-approval steps for new AWS account setup
- Covers enabling HPE SSO access via AWS Identity Center across different MPAs
  - See also [Additional AWS and IdC information](#additional-aws-and-idc-information)
- Details security guardrails, GitHub OIDC integration, CloudTrail logging, and Security Hub configuration
- Explains team responsibilities including timely PagerDuty response and defect tracking
- Covers optional IRSA (IAM Roles for Service Accounts) for keyless Kubernetes access to AWS resources

### Additional AWS and IdC information

#### [Providing Access to AWS Resources for Users](https://github.com/hpe-sre/platform-doc-portal/blob/main/docs/accts-subscrips/aws/aws-user-accts/access-aws-resources.md)

- Comprehensive guide to AWS IAM Identity Center management
- Details required creation order: organization account, member accounts, permission sets, users, groups, and assignments
- Covers user management for both GitHub users and additional users
- Explains group creation including custom groups and organizational unit level groups
- Details permission set management using AWS managed policies and custom permissions
- Provides default permission set requirements and account access group management

#### [Understanding the IdC Configuration File](https://github.com/hpe-sre/platform-doc-portal/blob/main/docs/accts-subscrips/aws/aws-user-accts/idc-config.md)

- Focuses on AWS account access procedures and IdC configuration file navigation
- Guides users to appropriate Business Unit configuration files
- Covers organizational best practices for group management and pull request workflows
- Includes team links for different organizations and their corresponding repositories
- Notes that file organization is subject to change as accounts move to new organizational units

## [Accessing your AWS account](https://github.com/hpe-sre/platform-doc-portal/blob/main/docs/accts-subscrips/aws/aws-user-accts/access-aws-accts.md)

**Note**: FinOps monitors or restricts usage to the AWS Marketplace as some offerings can be costly or outside budget controls. Therefore, a Service Control Policy (SCP) is in place regarding enabling a model in AWS Bedrock.

- Complete guide to accessing AWS accounts via SSO portals
- Provides organization-specific SSO links and IdC repositories for GLCS, CCP, Aruba, and Reference Architecture
- Covers CLI profile creation and AWS CLI configuration for Identity Center
- Details access request processes for CCP engineers (QA and production accounts) and BU engineers
- Includes troubleshooting for IdC loops and user access management procedures
- Features comprehensive team links table with SSO portals and repository locations

## Additional AWS information

### [Working with Account Lifecycle Requests](https://github.com/hpe-sre/platform-doc-portal/blob/main/docs/accts-subscrips/aws/acct-import.md)
- Comprehensive guide for account lifecycle operations including creation, deletion, and import
- Details information gathering requirements for account imports including root access, billing setup, Terraform usage, and security monitoring
- Emphasizes security best practices: no root logins, IAM Identity Center usage, and proper access management
- Covers user role definitions and break-glass procedures

### [Renaming an AWS Account](https://github.com/hpe-sre/platform-doc-portal/blob/main/docs/accts-subscrips/aws/aws-acct-rename.md)

- Detailed 364-line procedure for AWS account renaming
- Covers updating statefile backends, PDL (Platform Distribution List) changes, and Terraform state management
- Includes specific steps for legacy account handling and organization configuration updates
- Details S3 bucket migration, account email updates, and repository renaming procedures
- Provides commands for state file copying and validation

### [Enabling New Regions](https://github.com/hpe-sre/platform-doc-portal/blob/main/docs/accts-subscrips/aws/regions.md)

- Step-by-step guide for enabling new AWS regions (me-south-1 and ap-east-1)
- Covers Security Hub and GuardDuty configuration across multiple accounts
- Details provider setup, region standards configuration, and validation procedures
- Includes specific examples with PR references for unified-api accounts
- Covers STS endpoint enablement and manual intervention requirements
- AWS User Accounts Subdirectory


