1st version use - saml2aws and only handle tunneling part  
2nd version can implement custom saml2aws equivalent  

https://pkg.go.dev/github.com/versent/saml2aws/v2#section-readme  
This is based on python code from How to Implement a General Solution for Federated API/CLI Access Using SAML 2.0.  
https://aws.amazon.com/blogs/security/how-to-implement-a-general-solution-for-federated-apicli-access-using-saml-2-0/

This is what the tool does

Setup an account alias, either using the default or given a name
Prompt user for credentials
Log in to Identity Provider using form based authentication
Build a SAML assertion containing AWS roles
Optionally cache the SAML assertion (the cache is not encrypted)
Exchange the role and SAML assertion with AWS STS service to get a temporary set of credentials
Save these credentials to an aws profile named "saml"


we can extend this after credentials are saved to also optionally with a flag open a reverse tunnel via session manager to a jump host instance
jump host instance name or regex of it can be passed on command line or via predictable pattern

have to figure out the eks cluster list txt file as well - maybe it will be better to get the cluster automatically
