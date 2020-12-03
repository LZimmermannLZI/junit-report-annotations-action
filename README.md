# junit-report-annotations-action
Create an annotation of the build information and also list first n failed tests as seporate annotations

## Example
```
    - uses: KyleAure/junit-report-annotations-action@1.5
      if: always()
      with:
        name: "unit tests"
        path: "**/TEST-*.xml"
``` 
   
A demonstration is available here
https://github.com/ashley-taylor/junit-report-annotations-action-example

On a succesful run will get a summary like

![Pass](/../images/pass.png?raw=true "Pass")

On a failed run will get a image like this

![Fail](/../images/fail.png?raw=true "Fail")
