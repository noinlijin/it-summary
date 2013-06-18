```
base_dir=`pwd`
for f in `find -name description`; do 
  cd $base_dir
  cd `dirname $f`; 
  sudo -u git git gc; 
done;
```