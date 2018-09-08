

.. image:: https://travis-ci.org/katzenpost/playground.svg?branch=master
  :target: https://travis-ci.org/katzenpost/playground

.. image:: https://godoc.org/github.com/katzenpost/playground?status.svg
  :target: https://godoc.org/github.com/katzenpost/playground


Playground release
==================

This release of the Katzenpost mailproxy is to be used
with our public test mix network.

0. Install the github release of this software that is suitable
   to your operating system and hardware architecture.

1. Run the registration program to register your account on the mix network:
   ::

      ./registration -name alice

   The above example creates the "alice" user on the "playground" provider and is
   therefore addressed as ``alice@playground``.

   This registration process uses HTTPS without Tor by default. If you already
   have Tor on your system you can register using our onion service like this:
   ::

      ./registration -name alice -onion -torSocksAddr 127.0.0.1:9050


   Or if you run the Tor Browser Bundle with the default Tor setup then simply:
   ::

      ./registration -name alice -onion


2. The above command should have printed "Success" and created a ~/.mailproxy directory
   containing various coniguration files including key material. You will now be able
   to run mailproxy like so:
   ::
   
      ./mailproxy -f ~/.mailproxy/mailproxy.toml

3. Configure your e-mail client to use mailproxy. That is to say,
   mailproxy exposes POP3 and SMTP services which your e-mail client
   should be configured to use:
   ::

      POP3 at 127.0.0.1 on port 2524
      SMTP at 127.0.0.1 on port 2525

Contact
=======

Please do feel free to contact us for question or assistance.

* You can reach me directly via e-mail: dawuud@riseup.net

* I'm also available on IRC, my nick is ``dawuud`` in the #katzenpost channel on the OFTC network.

* We've also got a mailing list here: https://lists.mixnetworks.org/listinfo/katzenpost


license
=======

AGPL: see LICENSE file for details.


supported by
============

.. image:: https://katzenpost.mixnetworks.org/_static/images/eu-flag-tiny.jpg

This project has received funding from the European Union’s Horizon 2020
research and innovation programme under the Grant Agreement No 653497, Privacy
and Accountability in Networks via Optimized Randomized Mix-nets (Panoramix).
