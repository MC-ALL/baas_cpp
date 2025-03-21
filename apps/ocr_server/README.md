### Workflow
1. Build binaries
    - platforms : Windows, Linux, MacOS
    - BuildType : Release
    - Target    : BAAS_ocr_server

2. Test Code
    - Use python unittest to test all the api and check response
    - working directory : folder `BAAS_Cpp`
    - python version : 3.9.18
    - command : 
        1. install dependencies
            ```shell
               pip install -r apps/ocr_server/test/requirements.txt
            ```
        2. run test
           ```shell
              python -m unittest discover -s apps/ocr_server/test -p "*.py"
           ```
    If test passed:
3. Push binaries to corresponding repository
    - Windows: https://github.com/pur1fying/WindowsCompiled_baas_ocr_server.git
    - Linux: https://github.com/pur1fying/LinuxCompiled_baas_ocr_server.git
    - MacOS: https://github.com/pur1fying/MacOSCompiled_baas_ocr_server.git
    **note**: Only update changed files so that the ocr_server updater will not copy all the files every time.


### Known Issues
1. MacOS : python can't get shared memory by name.
2. MacOS & Linux : file logger create the log file but didn't write log.ß
3. api "get_text_boxes" is not implemented
4. need a method / api to shutdown the server    
5. update test code