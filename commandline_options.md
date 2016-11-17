# Command Line Options and Application Usage

Add beautiful command line options and usage descriptions to your program

**Example**
```sh
$ java -cp uploader.jar ExcelUploader

[2016-Nov-17 10:54:10]  *********************************************************
[2016-Nov-17 10:54:10]  Excel Uploader
[2016-Nov-17 10:54:10]  *********************************************************
Missing required options: excel, h, p, ns, d, u, pw, dp, rs, dt
usage: Excel Uploader
 -d,--domain <arg>           user domain
 -dp,--dirPrefix <arg>       local directory prefix
 -excel,--excel-file <arg>   full path to the excel file
 -h,--host <arg>             server hostname
 -p,--port <arg>             server port number
 -pw,--password <arg>        password
 -u,--username <arg>         username
  
```

Maven Repo
```xml
<dependency>
	<groupId>commons-cli</groupId>
	<artifactId>commons-cli</artifactId>
	<version>1.3.1</version>
</dependency>
```

Java code
```java
import org.apache.commons.cli.*;

Options options = new Options();
Option usernameOption = Option.builder("u")
  .required(true)
  .hasArg()
  .longOpt("username")
  .desc("username")
  .build();
options.addOption(usernameOption);

Option passwordOption = Option.builder("pw")
    .required(true)
    .hasArg()
    .longOpt("password")
    .desc("password")
    .build();
options.addOption(passwordOption);

CommandLineParser parser = new DefaultParser();
HelpFormatter formatter = new HelpFormatter();
CommandLine cmd;

try{
  cmd = parser.parse(options, args);
  String username = cmd.getOptionValue("username");
  String password = cmd.getOptionValue("password");  

} catch (PraseException e){
  System.out.println(e.getMessage());
  formatter.printHelp("Film Uploader", options);
  System.exit(1);
  return;
}
```
