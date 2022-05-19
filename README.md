# duppy: a RFC2136 dynamic DNS update server

This is a stand-alone server which implements both a subset of
[RFC2136](https://datatracker.ietf.org/doc/html/rfc2136) and offers
a simple HTTP API for performing dynamic DNS updates.

The intended audience for this software are DNS service providers
who store customer DNS data in a custom database, using something
like [bind's DLZ](https://kb.isc.org/docs/aa-00995).


## Project Status

[Roadmap and project status are Issue #1](https://github.com/pagekite/duppy/issues/1)



## Getting started

Installation:

     # Make sure the basics are installed
     apt install python3 python3-pip git virtualenv

     # Fetch duppy
     git clone https://github.com/pagekite.net/duppy

     # Install dependencies
     cd duppy
     virtualenv -p /usr/bin/python3 .env
     . .env/bin/activate
     pip install -r requirements.txt

Configuration:

    cd /path/to/duppy
    cp examples/duppy-simple.py duppy-local.py
    vi duppy-local.py

*Note:* the 'simple' example assumes you are using an SQL backend for
storing DNS records and shows how to configure that. If you are doing
something more excited/complicated, other examples may be better starting
points. Browse around!

Running the server:

    cd /path/to/duppy
    . .env/bin/activate
    python3 duppy-local.py


## Copyright, License, Thanks

Copyright (C) 2022, The Beanstalks Project ehf. and Bjarni R. Einarsson.

MIT License: See the file [LICENSE](LICENSE) for details.

Big thanks to the [async_dns](https://github.com/gera2ld/async_dns),
and [dnspython](https://www.dnspython.org/) projects! Without them this
would have been much more difficult.
