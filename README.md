apgpjs
======

JavaScript to have messages encrypted with PGP - e.g. for web/contact-forms


used Main source: http://www.hanewin.net/
* http://www.hanewin.net/encrypt/PGcrypt.htm
* http://www.hanewin.net/encrypt/PGdecode.htm
with a non-specific proprietary licence (all rights reserved, but put up to be used)


## how to start

just use the example 'myPGPencode.htm' and experiment with it.
it should be no problem...
* put in your key,
* check the details that can be used to identify you
* change it for e.g. a contact form


## how to get my email out of my key

you can either
* reuse your keys in place for a webform
* or create new ones (recommended)

to edit your existing key and delete an id with gpg on cli:

    gpg --editkey {keyid}

in gpg command line:

    adduid
    uid 1
    deluid
    save

back on cli:

    gpg --export -a {keyid} >pubkeyfile.asc
