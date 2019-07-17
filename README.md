## Amazon Ec2 Global Dashboard

Monitor how many EC2 instances are running across all regions with a simple dashboard.

Amazon EC2 Global Dashboard is created with a CloudFormation template. All elements of the dashboard are handled by the CloudFormation stack.

The goal of the dashboard is to give insight over all regions for how many instances are currently in a running state and over time to collect and monitor usage metrics. With the overall goal of keeping costs down and helping monitor your account.

The dashboard is populated by a Lambda function counting instances in a running state in each region, pushing them to CloudWatch as custom metrics. The stack can be created in any region.

Resources created by CloudFormation:
- AWS::CloudWatch::Dashboard       
- AWS::IAM::Role
- AWS::Lambda::Permission               
- AWS::Lambda::Function  
- AWS::Events::Rule

The Dashboard contains two widgets:

-        Running Instances – Dynamic widget showing the number of running instances and historical data.
The ‘Number’ widget type will show the current number of running EC2 instances in each region, this is the default view:

![NumberType.png](https://raw.githubusercontent.com/aws-samples/amazon-ec2-global-dashboard/master/media/NumberType.png)

The ‘Line’ widget type will show the historical data allowing the number of running EC2 instances to be monitored over the period of time defined:

![LineType.png](https://raw.githubusercontent.com/aws-samples/amazon-ec2-global-dashboard/master/media/LineType.png)

-        Region Mapping – Maps the region name with the region code and hyperlinks to the instances in each region. 

## License Summary

This sample code is made available under the MIT-0 license. See the LICENSE file.
