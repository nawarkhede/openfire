# openfire [3.9.3]

Code is bundled as eclipse project just clone it, and import in eclipse.

# Manually setup openfire code to eclipse

1. Download openfire source code from http://www.igniterealtime.org/downloads/source.jsp and unzip it.
2. Create java project in eclipse name it "openfire".
3. Open openfire folder from your local workspace in to explorer. This folder have bin,and src folder already with some other configuration files.
4. Also open unziped folder in explorer [which was downloaded eariler in step 1].
5. Go to unziped folder ```**[downloaded]**\openfire_src\src``` folder and copy all the folders except java folder and paste into ```workspace\openfire``` folder. As ```workspace\openfire``` folder already has bin folder so it will asked to you to replace or not. Make it replace.
6. Now go to ```openfire_src\src\java``` and copy all the files and folder to ```workspace\openfire\src``` folder.
7. Copy ```openfire_src\build``` folder to ```workspace\openfire``` folder.
8. Go to ```openfire_src\resources``` and copy ```i18n``` folder and paste in to ```workspace\openfire\resources```.
9. Now open eclipse and refresh ```openfire``` project.
10. Go to project properties Java Build Path > libraries > Add External Jars > and all the jars from following folders,

    * ```workspace\openfire\build\lib```
    *```workspace\openfire\build\lib\dist```
    *```workspace\openfire\build\lib\merge```
    *```workspace\openfire\build\lib\src```
11. Refresh the project from eclipse.
12. Go to run configurations from eclipse and right click on java application create new named openfire now search main class using search button, select ```org.jivesoftware.openfire.starter.ServerStarter``` and click ok.
13. Go to arguments tab and put VM arguments value as , ```-DopenfireHome="D:\workspaceluna\openfire"```
14. Go to classpath tab , click on ```user entries``` > click on advanced button on left > select add folder and select following folders
    * ```openfire\build\lib\dist``` click ok.
    * ```openfire\resources\i18n``` click ok.
    * ```openfire\resources\jar``` click ok.
15. Go to common tab and check the checkbox at debug and run. Click apply and close.
16. Now copy web folder from workspace and paste in to ```workspace\plugins\admin``` folder and rename it to ```webapp```.


# Problems ?
```
HTTP ERROR 500

Problem accessing /login.jsp. Reason:

    Unable to compile class for JSP
Caused by:

org.apache.jasper.JasperException: Unable to compile class for JSP
```

After spending long time in to this issue I came to know that eclipse was unable to add ```tools.jar``` file on classpath. So added ```tools.jar``` file in to classpath manually.




