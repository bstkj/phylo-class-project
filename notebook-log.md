## NEXUS
- http://informatics.nescent.org/w/images/8/8b/NEXUS_Final.pdf

---
## BEAST

### Installation (local machine)
- [BEAST-2.6.3 for Windows (w/ Java)](http://www.beast2.org/download-windows-with-jre/)

### Installing new packages (e.g. SNAPP)
- Do `packagemanager -add SNAPP`. The `packagemanager` script is located within BEAST installation (e.g. `beast/bin/packagemanager`). Reading it is helpful for understanding the BEAST/JAVA environment variables and how they are used.
- After a new package is installed, this change should be reflected (i.e. `<new package name>.addon.jar` should be appended to `package.path`) in the `beauti.properties` file located in the package directory.

### Running (on Cluster)
- Need to set `BEAST_PACKAGE_PATH` environment variable in job script to point to the BEAST package directory (e.g. `export BEAST_PACKAGE_PATH=<path to package directory>`)
- Need to have entry that points to SNAPP/lib/snapp.addon.jar in .beast/2.6/beauti.properties

### Multi-threading

### Adjusting transition kernels

### Debugging
- [Beast-users google-group](https://groups.google.com/g/beast-users)

---
## TRACER
### Useful tutorials
- https://beast.community/analysing_beast_output
- https://beast.community/tracer_convergence

### Why is the no. of states in the trace-plot greater than the no. of states in the trace-file?
- This is a bug that seems to arise from simultaneously viewing multiple trace files all with the same name. The issue is resolved by giving the trace files distinct names.  

### What is the `TreeHeightLogger` variable?
- Has the lowest ESS among the estimated quantities.

### Why do some `theta`s (ancestral effective population sizes) show more variation across their marginal density plots for different runs?

---
## Tree Set Analyzer
- `./AppLauncher.exe  TreeSetAnalyser -options`
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