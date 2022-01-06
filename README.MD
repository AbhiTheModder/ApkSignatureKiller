One-click cracking APK signature verification
 ==================

 Refer to [fourbrother/kstools](https://github.com/fourbrother/kstools), some improvements have been made on its basis, and it is implemented in pure Java.

 principle
 -----

 By inserting code into the Application entry, the getPackageInfo method of PackageManager in the program is hooked, and the signature information obtained by it is changed.

 Processing steps
 -------

 1. Read the signature information of the original APK.
 2. Replace or add the name attribute of application in AndroidManifest.xml.
 3. Read PmsHookApplication.smali and replace the signature information. If the original APK has customized Application, you also need to modify the parent class of PmsHookApplication, and finally compile smali and add it to classes.dex.
 4. Sign the exported APK.

 Instructions
 -------

 1. To use this tool, you need to install the Java environment first, and nkstool.jar is the compiled file.
 2. Modify the configuration information in config.txt as needed, and put the corresponding apk in the project root directory.
 3. Operation, three ways
     -Open the project with IDEA and run the source code.
     -Windows system can directly open run.bat to execute.
     -In Linux or MacOS system, open the terminal, cd to the project root directory, enter java -jar nkstool.jar and press Enter.
 4. Test the output apk file

 other
 ----

 If you don't need the source code, you can just keep nkstool.jar, config.txt, run.bat and other files.

 This tool is only valid for those applications that only use PackageManager.getPackageInfo().signatures to verify signatures.
