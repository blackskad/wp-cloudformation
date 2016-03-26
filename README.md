# wp-cloudformation
A cloudformation template to host a wordpress site.

## How to use this file

* Create an account on aws.amazon.com
* Register your domain with your preferred registrar
* Create a hosted zone in Route53, see http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/CreatingHostedZone.html
* Change the nameservers in your registrar config to point to the Route53 supplied nameservers. For more information, see http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/GetInfoAboutHostedZone.html
* Create a .tar.gz archive for your wordpress site. I suggest adding these plugins:
** amazon-s3-and-cloudfront
** amazon-web-services 
** wp-super-cache
In your wp-config.php, make sure you have these placeholders:
** define('DB_PASSWORD', 'DBPASSWORD');
** define('DB_HOST', 'DBHOSTNAME');
** define('AWS_ACCESS_KEY_ID', 'ACCESSKEY');
** define('AWS_SECRET_ACCESS_KEY', 'SECRETKEY');
* Create an S3 bucket with your domainname as bucket name
* Upload the wordpress archive to the newly created S3 bucket using the AWS console, see http://docs.aws.amazon.com/AmazonS3/latest/UG/UploadingObjectsintoAmazonS3.html
* In the AWS console start a cloudformation stack using the template in this repository, for more information see http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-console-create-stack.html#cfn-using-console-initiating-stack-creation

_Warning: deploying this on AWS can cost money. I'm not responsible for any cost you may incur._
