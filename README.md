# Java In VScode
Recently , i switch vscode from Eclipse as my develop editor.CAZ my latop(Macbook Air 2015) has a so low performance that i can drink a cup of tea when i was waitting for it's loading. 

In this repo i will share the problem i met when i use vscode. 




## about:  Java Extension Pack 
1. **Problem: vscode can not receive the input since it show the reuslt in debug console.** 
   solution:  use terminal to run the java file. somebody give solution that edit the launch.josn and add configure so java code  will run through External Terminal. However, it is not convinent. Although, the offical of extnsion do not provide Integrated Terminal configure, will still can use it. edit the launch.json in your project folder add this: 
   ```
      {
                "name": "java: Current File (Integrated Terminal)",
                "type": "java",
                "request": "launch",
                "console": "integratedTerminal",
                "mainClass": "${file}"
            },   
     ```

if you want to this configure works for all the new java project add this to setting.josn between{}
``` 
   "launch": {
        "configurations": [
            {
                "type": "java",
                "name": "Debug (Launch) - Current File",
                "request": "launch",
                "mainClass": "${file}"
            },
         
            {
                "name": "java: Current File (Integrated Terminal)",
                "type": "java",
                "request": "launch",
                "console": "integratedTerminal",
                "mainClass": "${file}"
            },
            
            {
                "type": "java",
                "name": "Debug (Launch) - External Terminal",
                "request": "launch",
                "console": "externalTerminal",
                "mainClass": ""
            }
        ],
        "compounds": []
    },
    
    ```
   

## Maven for Java Extension 

