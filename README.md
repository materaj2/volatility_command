# volatility_command
List of Volatility Command

# Process  
volatility -f [image] --profile = [OS Profile] pslist  
volatility -f [image] --profile = [OS Profile] psscan  
volatility -f [image] --profile = [OS Profile] pstree  
volatility -f [image] --profile = [OS Profile] psxview  
volatility -f [image] --profile = [OS Profile] psxview --apply-rules  

# Network
volatility -f [image] --profile = [OS Profile] netscan #Vista or later  
volatility -f [image] --profile = [OS Profile] connections #  
volatility -f [image] --profile = [OS Profile] connscan #  
volatility -f [image] --profile = [OS Profile] sockscan #  

# Registry
volatility -f [image] --profile = [OS Profile] hivelist  
volatility -f [image] --profile = [OS Profile] printkey -K "[registry key]"  
volatility -f [image] --profile = [OS Profile] userassist  
volatility -f [image] --profile = [OS Profile] shellbags  
volatility -f [image] --profile = [OS Profile] shellbags --output-file = [shellbags.body] --output = body  
volatility -f [image] --profile = [OS Profile] shimcache  
volatility -f [image] --profile = [OS Profile] getsids --offset [address]  
volatility -f [image] --profile = [OS Profile] privs --offset [address]  
volatility -f [image] --profile = [OS Profile] hashdump  
volatility -f [image] --profile = [OS Profile] lsadump  

# Command history
volatility -f [image] --profile = [OS Profile] cmdscan  
volatility -f [image] --profile = [OS Profile] consoles  

# DLL
volatility -f [image] --profile = [OS Profile] dlllist  
volatility -f [image] --profile = [OS Profile] handles -p [pid] -t File  
volatility -f [image] --profile = [OS Profile] handles -p [pid] -t Key  
volatility -f [image] --profile = [OS Profile] handles -p [pid] -t Directory  
volatility -f [image] --profile = [OS Profile] handles -p [pid] -t Port  
volatility -f [image] --profile = [OS Profile] handles -p [pid] -t Mutant  
volatility -f [image] --profile = [OS Profile] handles --offset [address]  
  
# evtlog  
volatility -f [image] --profile = [OS Profile] evtlogs -D [Directory]  
volatility -f [image] --profile = [OS Profile] evtlogs --save-evt -D [Directory]  
  
# Service  
volatility -f [image] --profile = [OS Profile] svcscan  
  
# FileSystem  
volatility -f [image] --profile = [OS Profile] mftparser --output-file = [outfile.txt]  
volatility -f [image] --profile = [OS Profile] mftparser --output-file = [outfile.txt] --output = body # body format can be read by other software  
  
# Dump  
volatility -f [image] --profile = [OS Profile] dlldump -p [pid] -D [Directory]  
volatility -f [image] --profile = [OS Profile] procdump -p [pid] -D [Directory]  
volatility -f [image] --profile = [OS Profile] dumpfiles -r .evtx $ --ignore-case -D [Directory]  
procdump -p [pid] --dump-dir = / tmp  
photorec / d [Directory] [image]  
  
# Timeline  
volatility -f [image] --profile = [OS Profile] timeliner --output-file = timeliner.body --output = body  
  
 # body files can be combined  
 cat [BodyFile.1] [BodyFile.2] [BodyFile.3]> [BodyFile]  
  
 # mactime  
 mactime --help  
 mactime -b [BodyFile] -d -z UTC  
  
# Vad  
volatility -f [image] --profile = [OS Profile] -p [pid] vadinfo  
volatility -f [image] --profile = [OS Profile] -p vaddump -D [Directory]  
  
# Strings  
strings -td -a [image] >> strings.txt # The word "FREE MEMORY" doesn't do anything but seems to be used often  
strings -td -el -a [image] >> strings.txt  
  
volatility -f [image] --profile = [OS Profile] strings -s strings.txt> [out.txt]  
  
grep [string] out.txt # Hook with IP address etc. and output before and after with -A -B option and investigate  
  
# Malware Check  
volatility -f [image] --profile = [OS Profile] ldrmodules -p [pid]  
volatility -f [image] --profile = [OS Profile] malfind -p [pid]  
  
# Yarascan
volatility -f [image] --profile = [OS Profile] yarascan --yara-rules = "[strings]"  
volatility -f [image] --profile = [OS Profile] yarascan -p [pid] --yara-rules = "[binary code]"  
volatility -f [image] --profile = [OS Profile] yarascan -p [pid] --yara-rules = "[strings]"  
  
# Misc  
volatility -f [image] --profile = [OS Profile] objtypescan # Object Acan  
volatility -f [image] --profile = [OS Profile] Volshell # Volshell  
volatility -f [image] --profile = [OS Profile] iehistory # IE history  
