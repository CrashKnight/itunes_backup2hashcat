# About

The goal of this project is to make it very easy to convert iTunes backup files to "hashes" which hashcat can crack with mode: -m 14700 or -m 14800

# Requirements

Software:  
- Perl must be installed (should work on *nix and windows with perl installed)

# Installation and first steps

* Clone this repository:  
    git clone https://github.com/philsmd/itunes_backup2hashcat.git  
* Enter the repository root folder:  
    cd itunes_backup2hashcat
* Run it:  
    ./itunes_backup2hashcat.pl Manifest.plist
* Copy output to a file (or redirect output to a file (>) directly) and run it with hashcat using mode -m 14700 = iTunes Backup < v10.0 or -m 14800 = iTunes Backup v10.x

If the output of itunes_backup2hashcat.pl start with $itunes_backup$*9* then you need to use hash mode -m 14700, for $itunes_backup$*10* use -m 14800 instead.

# Command line parameters 

The usage is very simple: you just specify the path to the 7-Zip file as the first command line argument.   
   
You can also use multiple files on the command line like this:   
  ./itunes_backup2hashcat.pl Manifest.plist Manifest2.plist   
  ./itunes_backup2hashcat.pl \*.plist   
  ./itunes_backup2hashcat.pl Manifests/\*   

# Explanation of the hash format 

if the backup was generated by IOS version less than 10:  
 $itunes_backup$\*9\*wkpy\*iter\*salt\*\*  
  
version 10.x hashes:  
 $itunes_backup$\*10\*wkpy\*iter\*salt\*dpic\*dpsl  

# Hacking / Missing features

* More features
* improvements and all bug fixes are very welcome 

# Credits and Contributors 
Credits go to:  
  
* philsmd, hashcat project

# License/Disclaimer

License: belongs to the PUBLIC DOMAIN
  
Disclaimer: WE PROVIDE THE PROGRAM “AS IS” WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE Furthermore, NO GUARANTEES THAT IT WORKS FOR YOU AND WORKS CORRECTLY
