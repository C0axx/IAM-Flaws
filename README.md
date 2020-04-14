# IAM-Flaws
## AWS IAM Security Toolkit: CIS Benchmarks | Enumeration | Privilege Escalation

A simple bash script that checks for misconfigurations in User and Group Policy Permissions in order to escalate privileges.

**It is recommended to go through this Blog before proceeding:**</br>
https://theblocksec.com/2020/04/14/iam-flaws-exploiting-user-and-group-policies-in-aws-iam/

As of now, the script supports the following activities:

- All CIS Benchmark checks related to AWS IAM
- AWS IAM Enumeration of Users, Groups, Policies and Permissions
- Privilege Escalation Scanning
- Privilege Escalation Exploitation

## Requirements
#### git clone https://github.com/nikhil1232/IAM-Flaws/
#### cd IAM-Flaws
#### pip install -r requirements.txt
#### apt-get install jq

Once awscli is installed, you need to configure it using the **aws configure** by providing the access and the secret key of the IAM user.

Now coming to permissions, there are a few permissions that needs to be set for a user in order for our enumeration script to work properly and for an effective and complete enumeration.
Below is listed a few permissions that is recommended to be set for a user before proceeding with our script.

“iam:GetUser”

“iam:ListUsers”

“iam:ListGroupsForUser”

“iam:ListGroupPolicies”

“iam:GetGroupPolicy”

“iam:ListAttachedGroupPolicies”

“iam:GetPolicy”

“iam:GetPolicyVersion”

“iam:ListUserPolicies”

“iam:GetUserPolicy”

“iam:ListAttachedUserPolicies”

These permissions could be set either through the awscli or directly through the console, however if you don’t provide these permissions, the script will try to enumerate as much as possible based on the permission a certain user has.

## Usage 
#### bash iam-flaws.sh

There are 3 different modules/scripts for benchmark checks, enumeration and privilege escalation respectively and all the 3 of them could be run independently, however it is highly recommended to use iam-flaws.sh directly which is kind of a central script through which you could select any of the module and it would also help in storing your output to a file.
