a PGP JavaScript 
================

JavaScript to have messages encrypted with PGP - e.g. for web/contact-forms
this has been collected and written by Herbert Hanewinkel, [haneWIN](http://www.hanewin.net/)

There is a superior implementation with [OpenPGPJS](http://openpgpjs.org/), but it works with modern browsers only


## examples and demos

* [encryption demo by haneWIN](http://www.hanewin.net/encrypt/PGcrypt.htm)
* [decryption demo by haneWIN](http://www.hanewin.net/encrypt/PGdecode.htm)
* [contact form demo by haneWIN](http://c1.hanewin.net/)

other appearances
* [Privacy Dresden](https://privacydresden.noblogs.org/kontakt/)


## Q&A

### why?

#### why using (this) javascript

1. because it makes sense to encrypt communikation although email is not secure at least the information transported in the body can be secured
2. e.g. you can be contacted by customers via a web form and they do not need to fear someone reading the credentials they had to give for proper identification and verification
3. to enable people that do not have a dedicated email client or an own machine to send you encrypted email

#### why using PGP

Read what the innivator wrote [about the need](http://www.pgpi.org/doc/whypgp/en/) for his work ([available translations](http://www.pgpi.org/doc/whypgp/))

### how to start

just use the example 'myPGPencode.htm' and experiment with it.
it should be no problem...
* put in your key,
* offline-check the details that can be used to identify you
* change it for e.g. a contact form
* give pull requests if you improved things


### how to get my email address out of my key

you can either
* reuse your keys in place for a webform
* or create new ones (recommended)

to edit your existing key and delete an id with gpg on cli as well as existing signatures:

    gpg --editkey {keyid}

in gpg command line:

    adduid
    uid 1
    deluid
    minimize
    save

back on cli:

    gpg --export -a {keyid} >pubkeyfile.asc

for more information read [GnuPG docs](http://www.gnupg.org/documentation/) or the documentation of your native PGP client


### how to display PGP public key information and which

for proper identification and to avaoid unwanted usage of duplicate or forged IDs and fingerprints you should always provide at least
* key-size
* keyID
* fingerprint

there is the possibility of [forged public keys](http://www.pgp.net/pgpnet/pgp-faq/pgp-faq-keys.html#key-public-key-forgery), but if someone manages to create a second key with identical fingerprint and keyID it is implausible to have still the same key-size

optionally it is good to provide additionally
* a link to a copy of the public key (e.g. on a keyserver)
* date of key-creation
* used algorithms
* information how others can use it

#### example of the keyID e.g. on a website

    haneWIN Team
    EMail: mail@hanewin.de
    contact form: http://c1.hanewin.net/
    1024D/95622A07 created on 2002-08-11
    fingerprint: 9D54 F723 23E4 7428 AA9F 343C C112 D2F6 9562 2A07
    Algorithms: DSA and Elgamal
    
[public key file](http://pgp.mit.edu/pks/lookup?op=get&search=0xC112D2F695622A07)
[how to use PGP on your pc](https://www.riseup.net/en/howto-gpg-keys)

#### compact example e.g. for business cards or email templates

    EMail: mail@hanewin.de
    PGP-keyID: 1024 DSA 9562 2A07
    fp: 9D54 F723 23E4 7428 AA9F
        343C C112 D2F6 9562 2A07


## License(s)

no warranties of any kind

the parts have been written by different people under different licenses, these are included in the source code of the files and have to be deployed with any copy.
