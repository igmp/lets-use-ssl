# Let's Use SSL
Use numerous Let's Encrypt certificates and have them all in one place.

If you have a few dozens of SSL certificates scattered over dozens of servers, this Ansible role can
help you.  This is how SSL certificates are managed at [Skyeng](http://skyeng.ru) and you can use
this method as well.  With this role you can easily manage large number of short-termed SSL
certificates without an army of Certbots.  Details are
[here](https://habr.com/ru/company/skyeng/blog/497432/) (in Russian).

The only requirement is to have DNS at AWS Route53.  However this can easily be changed in favour of
your favorite DNS provider.

Just describe all SSL certificates you need in `vars` subdirectory, one in a file like this:
```yaml
foo.example.com:
  alt_names:
    - bar.example.com
      baz.example.com
```
run one playbook and that's all.  Run this playbook from time to time.  And use the certificates
from this store whenever and wherever you need them.  They are guaranteed to be fresh.

[More info](vars/README.md) on how to describe the certificates.

## Example Playbook
```yaml
- hosts: localhost
  gather_facts: no
    roles:
      - lets-use-ssl
```

## Author Information
This role was written in 2019-2020 by [Igor Plekhov](https://www.linkedin.com/in/igor-plekhov).

The original place of this repo is at <https://github.com/igmp/lets-use-ssl>.
