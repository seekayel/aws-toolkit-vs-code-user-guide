# Setting Up Your AWS Credentials<a name="setup-credentials"></a>

To access Amazon Web Services \(AWS\) with the AWS Toolkit for Visual Studio Code, you must make your AWS account credentials available to the toolkit\. To use AWS\-supported credentials, continue reading in this topic\. To use an external credential process, see [Using an External Credential Process](external-credential-process.md)\.

**Note**  
Some features of the Toolkit for VS Code, such as creating a serverless application, don't require AWS credentials\.

## Get Your AWS Access Keys<a name="setup-credentials-get-access-keys"></a>

If you don't already have appropriate AWS access keys to store in your shared AWS config file or your shared AWS credentials file, you must get them now\.

To do so, see [Obtaining AWS Access Keys](obtain-credentials.md)\.

## About Shared AWS Files<a name="setup-credentials-about-files"></a>

Your *shared AWS config file* and your *shared AWS credentials file* are files that you can use to store configuration and credential information for AWS\. By default, these files are located in the `.aws` directory within your home directory and are named `config` and `credentials`, respectively\. For more information, see [Where Are Configuration Settings Stored?](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html#cli-configure-files-where) in the *[AWS Command Line Interface User Guide](https://docs.aws.amazon.com/cli/latest/userguide/)*\.

The Toolkit for VS Code locates and uses AWS access keys through your shared AWS config file and your shared AWS credentials file\. This is the method that is used by the AWS CLI and the AWS SDKs\. Access keys that you enter in the Toolkit for VS Code are saved to one of these files\.

These shared files can contain the credentials for more than one AWS account, stored as *profiles*\. Multiple accounts can be useful, for example, to provide developers and administrators with separate resources for development and for release or publication\.

## Add Your AWS Access Keys to Your Environment<a name="setup-credentials-set-access-keys"></a>

If you have already set your AWS credentials \(for example, by using the [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html)\), the Toolkit for VS Code will automatically detect those credentials and make them available to the toolkit\. If you haven't already set your AWS credentials, or if you want to include additional AWS credentials in your environment or update an existing credentials profile, you can do so through the Toolkit for VS Code, as shown here\.

**Note**  
As an alternative to these procedures, you can use the [aws configure](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html) AWS CLI command to add AWS credentials to your environment\. You can also use aws configure to set the default AWS Region, which is needed for certain operations such as creating a serverless application\.

### Create the Shared AWS Credentials File<a name="create-shared-cred-file"></a>
+ If you already have a shared AWS credentials file, you can skip to the [next procedure](#update-shared-cred-file)\.
+ If you already have a shared AWS *config* file and want to use it, you can skip to the [next procedure](#update-shared-cred-file)\.
+ If you have only a shared AWS *config* file but do NOT want to use it, you must first create a shared AWS credentials file by using techniques that are normal for your operating\-system\. After that, you can skip to the [next procedure](#update-shared-cred-file)\.

Follow these steps to create the shared AWS credentials file\.

1. Open VS Code\.

1. To open the **Command Palette**, on the menu bar, choose **View**, **Command Palette**\. Or use the following shortcut keys: 
   + Windows and Linux – Press **Ctrl\+Shift\+P**\.
   + macOS – Press **Shift\+Command\+P**\.

1. Search for **AWS** and choose **AWS: Create Credentials Profile**\.  
![\[AWS Toolkit command palette.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-cmd-create-cred.png)

1. Enter a name for the initial profile\.  
![\[AWS Toolkit create profile, enter name.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-cmd-create-first-cred-profile-name.png)

1. Enter the *access key ID* for the credentials\. If you don't have an access key ID, see [Obtaining AWS Access Keys](obtain-credentials.md)\.  
![\[AWS Toolkit create profile, enter access key ID.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-cmd-create-first-cred-profile-access.png)

1. Enter the *secret access key* for the credentials\. If you don't have a secret access key, see [Obtaining AWS Access Keys](obtain-credentials.md)\.  
![\[AWS Toolkit create profile, enter secret access key.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-cmd-create-first-cred-profile-secret.png)

After you complete this procedure, you can verify the shared AWS credentials file by opening it directly or by performing the first three steps of the next procedure \(without making any updates\)\.

### Update one of Your Shared Files<a name="update-shared-cred-file"></a>

Follow these steps to add a new profile to your existing shared AWS config file or shared AWS credentials file\. You can also update an existing profile\.

1. Open VS Code\.

1. To open the **Command Palette**, on the menu bar, choose **View**, **Command Palette**\. Or use the following shortcut keys: 
   + Windows and Linux – Press **Ctrl\+Shift\+P**\.
   + macOS – Press **Shift\+Command\+P**\.

1. Search for **AWS** and choose **AWS: Create Credentials Profile**\.  
![\[AWS Toolkit command palette.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-cmd-create-cred.png)

1. When one or both of the shared files opens in the VS Code editor, add or update a profile\.

1. When you're finished updating the file, save it\.