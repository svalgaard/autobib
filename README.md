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

Setup or updating a profile is done using `--user`, `--password` and/or `--hostname`, e.g.,

```
    autobib --user CPR --password 1234 --hostname odensebib.dk Peter
```

This updates the `[Peter]` section in `~/.autobibrc` with an "encrypted" CPR number and password.

If only a profile name is provided, the books corresponding to this user
is renewed:

```
    autobib Peter
```

crontab
=======

One way to use autobib is to add a few lines to your crontab, e.g.,
```
0 7 */3 * * /path/to/autobib Peter
0 7 */3 * * /path/to/autobib --html -e e@example.net Peter | sendmail -ti
```
