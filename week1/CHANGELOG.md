# Change history for CB99 wordpress cloudformation stack

## 0.2.6

*   change sshkey from parameter to map value by region
*   add .remarkrc (markdown linter config)

## 0.2.5

*   fix incorrect reference for source security group in DBSecurityGroup ingress rule
*   fix incorrect reference for security group in DBInstance
*   fix invalid default for DBSize parameter
*   change DBSecurityGroup to RDS security group
*   updated AMI for us-west-2 to custom Wordpress AMI
*   updated/added cfn-init

## 0.2.4

*   reordered resource to ensure dependencies are created before they are used

## 0.2.3

*   fixed typo in ELB health check

## 0.2.2

*   changed Ref functions to Fn::GetAtt for security group IDs

## 0.2.1

*   added ELB DNS Name to Outputs

## 0.2.0

*   added DBInstance & WPAutoScalingGroup

## 0.1.2

*   added WPLaunchConfig

## 0.1.1

*   added WPELBSecurityGroup

## 0.1.0

*   Initial commit, week 1 CFN template, week 2 term project notes
