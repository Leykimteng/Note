#### Fix conflig between libre Office 
* sudo apt-get remove openoffice-debian-menus  
if That doesn't work use this 
* sudo dpkg -r --force-all openoffice-debian-menus  
* sudo apt-get install -f  

dpkg -r mean remove dpkg 
 `--force-thing` for to do sth and `--force-all` mean set all force option  
 