# Junit Analysis for Github Actions
Creates an annotation for each Junit error or failure.
This actions is fork friendly as it does not require access to parent repository's access-token
However, if you do provide a token more detailed information will be output within the annotations.

## Configuration elements
access-token:

  description: "github token"
  
  required: false
  
path:

  description: "Glob to junit xml files"
 
  required: true
  
  default: "**/TEST-*.xml"
  
includeSummary:

  description: "Include a summary annotation"
  
  required: true
  
  default: true
  
numFailures:

  description: "Max number of failed tests to annotate"
  
  require: true
  
  default: 10
  
debug:
  description: "Log debug messages"
  
  require: true
  
  default: false
  
name:
  description: "Name of the check in the github actions UI"
  
  require: true
  
  default: "Junit Results"
  
## Action Examples
```
    #Without access token
    - uses: KyleAure/junit-report-annotations-action@1.5
      if: always()
      with:
        name: "unit tests"
        path: "**/TEST-*.xml"

    #With access token
    - uses: KyleAure/junit-report-annotations-action@1.5
      if: always()
      with:
        name: "unit tests"
        path: "**/TEST-*.xml"
        access-token: ${{ secrets.GITHUB_TOKEN }}
``` 

# Result Examples

A demonstration is available here
https://github.com/ashley-taylor/junit-report-annotations-action-example

> On a succesful run will get a summary annotation
> This will only be produced if an access-token was provided

![Pass](/../images/pass.png?raw=true "Pass")

--- 

> On a failed run will get a summary annoation, and individual test failure annoations
> This will be produced regardless of access-token

![Fail](/../images/fail.png?raw=true "Fail")
