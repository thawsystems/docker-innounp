[![](https://images.microbadger.com/badges/version/thawsystems/innounp.svg)](https://microbadger.com/images/thawsystems/innounp "Get your own version badge on microbadger.com") [![](https://images.microbadger.com/badges/image/thawsystems/innounp.svg)](https://microbadger.com/images/thawsystems/innounp "Get your own image badge on microbadger.com")

# Usage

```sh
mbp:~ dave$ docker run -it --rm --network=none -v ~/inno-files:/inno-files thawsystems/innounp

innounp@30e7abf9fac3:~$ innounp
innounp, the Inno Setup Unpacker. Version 0.46
Usage: innounp [command] [options] <setup.exe or setup.0> [@filelist] [filemask ...]
Commands:
  (no)   display general installation info
  -v     verbosely list the files (with sizes and timestamps)
  -x     extract the files from the installation (to the current directory, also see -d)
  -e     extract files without paths
  -t     test files for integrity
Options:
  -b     batch (non-interactive) mode - will not prompt for password or disk changes
  -q     do not indicate progress while extracting
  -m     extract internal embedded files (such as license and uninstall.exe)
  -pPASS decrypt the installation with a password
  -dDIR  extract the files into DIR (can be absolute or relative path)
  -cDIR  specifies that DIR is the current directory in the installation
  -n     don't attempt to unpack new versions
  -fFILE same as -p but reads the password from FILE
  -a     extract all copies of duplicate files
  -y     assume Yes on all queries (e.g. overwrite files)

innounp@30e7abf9fac3:~$ innounp -x -d/inno-files/extracted -popenwall -b /inno-files/setup.exe
; Version detected: 5500
#1 {app}\test.txt
Reading slice Z:\inno-files\setup.exe
#2 install_script.iss

innounp@30e7abf9fac3:~$ exit

mbp:~ dave$ ls -l ~/inno-files/extracted/\{app\}/
total 0
-rwxrwxrwx 1 root root 0 Jul 24 22:44 test.txt
```
