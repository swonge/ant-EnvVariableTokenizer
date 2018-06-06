# ant-EnvVariableTokenizer
using Ant script to replace the any config file (with .template file extension) under src-root property with the root directory containing the tokenized files (@XXX@)

reference from: https://stackoverflow.com/questions/15987556/ant-replacing-strings-in-specified-files-using-file-with-properties

FEATURE(S):
- replace strings matched in specific (with file extension .template) template file
- other static file (without .template file extension) remain intact
- static file will copy to target filtered folder intact
- The ANT <copy> task cannot "self-copy" files. So, for each matched file we'll have <copy> read the file, replace the  tokens, and write the result to a temporary file. Then, we'll  use another ANT <move> task to replace the original files with the  modified files.

PREREQUISITES
- Apache ANT 1.10.3 (this is where the buidl script is writen and test on)

prerequisites


USAGE:
	ant -Denv={environment specific properties file}
	
	- NOTE: environment specific properties file is required
	
	For example,
	- ant -Denv=Dev
	- ant -Denv=QA
	- ant -Denv=SIT
	
	
	
