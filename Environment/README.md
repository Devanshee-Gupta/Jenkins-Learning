# Environment variables


1. An environment directive used in the top-level pipeline block will apply to all steps within the Pipeline.
2. An environment directive defined within a stage will only apply the given environment variables to steps within the stage.
3. The environment block has a helper method credentials() defined which can be used to access pre-defined Credentials by their identifier in the Jenkins environment. 

```

Let's say, JENKINS_CREDS = credentials('<identifier_In_Jenkins_Environment>')
Then, two additional environment variables will be automatically defined: 
JENKINS_CREDS_USR and JENKINS_CREDS_PSW to access username and password respectively.

```
