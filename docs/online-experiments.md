## Running online experiments

We use PCIbex to create online experiments. If you're new to Ibex, we recommend you complete [this tutorial](https://doc.pcibex.net/basic-tutorial/).

To include multimedia resources in your experiment view this [guide](https://doc.pcibex.net/how-to-guides/managing-resources/).
* We use [dreamhost](https://www.dreamhost.com/wordpress/woocommerce-hosting/?gclid=CjwKCAjwsJ6TBhAIEiwAfl4TWF6Crd3Z2LW8N6cwguMU7OrJlJgYvqABd2vCAHhZkzxY5enjrtkmdBoCoK0QAvD_BwE) to host our media. Contact the lab manager for account information. 
    * To add media to dreamhost you can use the web ftp by simply logging in or connect via a client, like [FileZilla](https://filezilla-project.org/). 
        * You can also connect to dreamhost via the finder window if you are on a mac. _Note that web ftp uploads are limited to 1GB_.
    * More information on FTP and dreamhost can be found [here](https://help.dreamhost.com/hc/en-us/articles/115000675027-FTP-overview-and-credentials).

After you are added to the lab bucket (To be added to our lab bucket see [onboarding](onboarding.md)) You can download your data using Amazon Web Services (AWS). 

Setup
1.	Install the [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
2.	Open a command prompt terminal and type: aws configure sso
3.	You will be invited to enter a URL, type or copy-paste: `https://upenncloudsolutions.awsapps.com/start`
4.	If your browser does not open automatically, open a new browser window and visit the URL you see in your command prompt terminal, and enter the confirmation code you see in that same terminal
5.	Sign in using your pennkey and password
6.	Once signed in, return to the command prompt terminal and, when invited, select the region `us-east-1`
7.	Accept the default values for the different settings &mdash; choose an easy value like penn for example for the last setting (profile name)
8.	You are now all set up to access your bucket

Use
1.	_you can skip this step if you just configured your setup_
 In a command prompt terminal, type `aws --profile penn sso login`, replacing penn with the value you chose in step 7 above
2.	If your browser does not open automatically, open a new browser window and visit the URL you see in your command prompt terminal, and enter the confirmation code you see in that same terminal
3.	Sign in using your pennkey and password
4.	Once signed in, return to the command prompt terminal and list your results files by typing `aws --profile penn s3 ls s3://pcibex.penn.collection.BUCKETNAME/USERNAME/EXPERIMENTNAME/`, replacing (only the first) penn with the value from step 7 above, `BUCKETNAME` with your group's bucket name (eg. florianslab), `USERNAME` with the exact username you use on upenn.pcibex.net (case-sensitive) and `EXPERIMENTNAME` with the exact name of your experiment (case-sensitive, make sure to insert a backslash character \ before any space character)
5.	You can download all the CSV results files to your home folder by typing `aws --profile penn s3 cp s3://pcibex.penn.collection.BUCKETNAME/USERNAME/EXPERIMENTNAME/ ./ --recursive --exclude "*" --include "*.csv"` (applying the same substitutions as in the previous step)
6. Use `"*.zip"` to download video or audio recordings.