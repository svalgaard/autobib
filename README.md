autobib
=======

Automatically renew your library books.

Supported libraries:

* University Library of Southern Denmark (alvis-bib.sdu.dk)
* Odense Bibliotekerne (odensebib.dk)
* and most other public Danish municipality libraries

Requirements
============

* Python 3
* Python 3 libraries: MechanicalSoup, lxml

```console
# First check, that you are using pip for Python 3
# You may need to run pip3 instead of pip
user@sputnik:~/autobib$ pip -V
pip 18.0 from /.../pip (python 3.6)

user@sputnik:~/autobib$ sudo pip install -r requirements.txt
```

Setup + Usage
=============

Setup or updating a profile is done using --user, --password and/or --hostname
    %(prog)s --user CPR --password 1234 --hostname odensebib.dk Peter
This updates the [Peter] section with an "encrypted" CPR number and password.

If only a profile name is provided, the books corresponding to this user
is renewed:
    %(prog)s Peter

One way to use this is to put it in your crontab using a line like of the
```
0 12 1,16 * * /path/to/%(prog)s Peter
0 12 1,16 * * /path/to/%(prog)s --html -e e@example.net Peter | sendmail -ti
```
