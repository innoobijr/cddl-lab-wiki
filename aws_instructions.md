# AWS Instructions

## I. IAM Management
* --> create user with CLI and Dashboard access
* --> Apply IAM controls
* --> Create user directories: create and get public keys for access
* --> Users and groups: for software management
* --> Install packages and software for global access
* --> Security Group can allow any outgoing HTTP/HTTPS access. Depends: if you are not expecting to need outgoing traffic then kill it. Incoming traffic should just be SSH.
* --> Access to applications hosted on instance is via SSH Tunneling. The safest way that does require complex VPNs or exposing to public.

[New User Accounts for Linux Instance w/ SSH Access](https://aws.amazon.com/premiumsupport/knowledge-center/new-user-accounts-linux-instance/)


## II. Choosing an Instance
* --> Decide who creates instance and has access to key pem. 
* --> Go with Ubuntu image
* --> t or m family: t costs less and it performant as an analystics server. Paralleization limited by # of cores. Always possible repartition disk space after the fact. No possible with memory
* --> Decide computing environment (Python standard or Dask; PyTorch; PySpark)
	* --> Long-running vs. Compute (standalone vs. cluster)
* ----> Run as always on analytics cluster. Not expension via compute hours. 
* ----> Resource-sharing: how many people; how many processes? Individual management or admin
* ----> Create Images: Start instance; install packages; create image. Start new cluster when needed


## III. Securing AWS Resources 
* PM should create IAMs and assign appropriate access to user.
* Service-Level roles
* Administrative roles
* User Groups and Role to Manage access resolution

## IV. Configuring IAM AWS access
* aws configure

## V. Environments
**Anaconda Environments**: Python files start to get pretty large. Central management is much better. Depends on size of group. Always work in an environment.
**Jupyter Hub**: makes it easy to view and manage multiple notebooks

[Ananconda Multi-user](https://docs.anaconda.com/anaconda/install/multi-user/)


* Baseline:
	* ALWAYS USE IAM
	* TIGHTEN FIREWALL
