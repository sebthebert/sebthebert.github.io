# Ansible Contribution

http://docs.ansible.com/ansible/latest/community.html#contributing-code-features-or-bugfixes

```
git clone https://github.com/sebthebert/ansible.git
cd /ansible
./hacking/test-module -m lib/ansible/modules/files/find.py -a '{"path":"/ansible/lib/ansible/modules", "pattern":".+/files/.+py$", "use_regex":"yes", "recurse":"yes"}'
```
https://github.com/ansible/ansible/blob/devel/CONTRIBUTING.md

Then, I made my first Ansible Pull Request: [Improve 'find' module with pattern search not limited to basename](https://github.com/ansible/ansible/pull/33488)
