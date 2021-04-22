## NEXUS
- http://informatics.nescent.org/w/images/8/8b/NEXUS_Final.pdf

---
## BEAST

### Installation (local machine)
- [BEAST-2.6.3 for Windows (w/ java)](http://www.beast2.org/download-windows-with-jre/)

### Installing new packages (e.g. SNAPP)
- Do `packagemanager -add SNAPP`. The `packagemanager` script is located within BEAST installation (e.g. `beast/bin/packagemanager`). Reading it is helpful for understanding the BEAST/JAVA environment variables and how they are used.
- After a new package is installed, this change should be reflected (i.e. `<new package name>.addon.jar` should be appended to `package.path`) in the `beauti.properties` file located in the package directory.

### Running (on Cluster)
- Need to set `BEAST_PACKAGE_PATH` environment variable in job script to point to the BEAST package directory (e.g. `export BEAST_PACKAGE_PATH=<path to package directory>`)
- Need to have entry that points to SNAPP/lib/snapp.addon.jar in .beast/2.6/beauti.properties

### Multi-threading

### Debugging
- [Beast-users google-group](https://groups.google.com/g/beast-users)

---
## JAVA 
### What does the `java` command do?
- Starts a Java application by (1) starting the JVM, (2) loading the specified class, and (3) calling that class's `main()` method.
- See [option descriptions](https://docs.oracle.com/en/java/javase/13/docs/specs/man/java.html).

### What is the `JAVA_HOME` environment variable for?
- Indicates the directory where JRE/JDK is installed. This may be used by Java-dependent software. 
- Note that OS uses `PATH` variable instead to find JRE/JDK. 
- Setting this variable (e.g. `export JAVA_HOME=jdk-install-dir`) is relevant when there are multiple versions of Java installed, or if JRE/JDK to be used is packaged with BEAST. 

### Java error messages
- `java.lang.NullPointerException`
- `java.io.IOException: Permission denied`
- `java.lang.UnsupportedClassVersionError`
    
    - Class file compiled for a newer Java version than the version of runtime trying to load the class.
    - See http://webcode.lemme.at/2017/09/27/java-class-file-major-minor-version/ for more details.

---