# まずは
sudo apt update
sudo apt upgrade
LANG=C name=xdg-user-dirs-gtk-update
# ansible install
sudo apt install ansible
# ansibleがsshを通して操作するので
sudo apt install openssh-server
sudo apt install net-tools
ssh key-gen -t rsa
cat ~/.ssh/id_rsa.pub > ~/.ssh/authorized_keys

# localhostとして設定
```/etc/ansible/hosts
[local-server]
localhost
```
`ansible local-server -a "cat /etc/hosts"`で好きなコマンドを打てる

`ansible-playbook start.yml --ask-become-pass`でyml実行

`chsh`は手動