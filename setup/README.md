## Lab Setup

Requirements:

* AWS CLI
* AWS Console Access

### Step 1

Clone the repository:

```
git clone https://github.com/starchx/devlab-eks-alb-2048game.git
cd devlab-eks-alb-2048game
```

### Step 2

Create Cloud 9 CloudFormation stack

```
cd setup
./cloud9.sh
```

### Optional Step

If AWS Console login is not the same user as AWS CLI, the Cloud 9 environment created can not be used by AWS Console user until it is shared. To share the environment with AWS Console user:

* Update share-cloud9.sh Line #6 with ARN of Console User:

```
AWS_CONSOLE_USER_ARN=<AWS CONSOLE LOGIN ARN>
```

* Run the script to share the environment:

```
./share-cloud9.sh
```

### Step 3

Navigate to AWS Cloud 9 Console, find the environment and open IDE. The environment title starts *EKSCloud9* and has *DevLab EKS ALB 2048 Game Cloud9 environment* in description. The following steps to be completed on Cloud 9 environment.

### Step 4

Disable Cloud 9 Managed Credentials

* Top menu **AWS Cloud9** and choose **Preferences**
* Left menu **AWS SETTINGS** and choose **Credentials**
* Disable AWS managed temporary credentials:

![Disable Cloud 9 Managed Credentials](https://raw.githubusercontent.com/starchx/devlab-eks-alb-2048game/master/setup/disable-cloud9-credentials.png "Disable Cloud 9 Managed Credentials")

### Step 5

Clone the repository again via Cloud 9 terminal:

```
git clone https://github.com/starchx/devlab-eks-alb-2048game.git
cd devlab-eks-alb-2048game
```

### Step 6

Run bootstrap.sh from Cloud 9 to create EKS cluster

```
cd setup
./bootstrap.sh
```

## Lab Reset

Run reset.sh from Cloud 9 to reset for next customer

```
cd setup
./reset.sh
```

## Lab Clean Up

Run cleanup.sh from Cloud 9 to create EKS cluster

```
cd setup
./cleanup.sh
```

Delete the Cloud 9 CloudFormation stack named **devlab-eks-alb-2048game** from AWS Console

Delete the EKS CloudFormation stack named **eksctl-eks-alb-2048game-cluster** if the auto deletion was failed.
