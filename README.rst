

.. image:: https://travis-ci.org/katzenpost/playground.svg?branch=master
  :target: https://travis-ci.org/katzenpost/playground

.. image:: https://godoc.org/github.com/katzenpost/playground?status.svg
  :target: https://godoc.org/github.com/katzenpost/playground


Playground release
==================

**Katzenpost is still pre-alpha.  DO NOT DEPEND ON IT FOR STRONG SECURITY OR ANONYMITY.**


This release of the Katzenpost mailproxy is to be used with our public
test mix network. Furthermore you should expect us to remove this free
service when our testing period is over at some arbitrary time in the
future.


0. Install the latest github release of this software (versions v0.0.2 or later)
   that is suitable to your operating system and hardware architecture, found here:

   * https://github.com/katzenpost/playground/releases

1. Run the registration program to register your account on the mix network:
   ::

      registration -name alice

   The above example creates the "alice" user on the "playground" provider and is
   therefore addressed as ``alice@playground``.

   This registration process uses HTTPS without Tor by default. If you already
   have Tor on your system you can register using our onion service like this:
   ::

      registration -name alice -onion -torSocksAddr 127.0.0.1:9050


   Or if you run the Tor Browser Bundle with the default Tor setup then simply:
   ::

      registration -name alice -onion


2. The above command should have printed "Success" and created a ~/.mailproxy directory
   containing various coniguration files including key material. You will now be able
   to run mailproxy like so:
   ::
   
      mailproxy -f ~/.mailproxy/mailproxy.toml

3. Configure your e-mail client to use mailproxy. That is to say,
   mailproxy exposes POP3 and SMTP services which your e-mail client
   should be configured to use:
   ::

      POP3 at 127.0.0.1 on port 2524
      SMTP at 127.0.0.1 on port 2525

   Here's one possible solution:
   1. install thunderbird::

        sudo apt install thunderbird

   2. Launch thunderbird and go to the Edit menu:

      * select Account Settings

      * click on the ``Account Actions`` drop down menu and select
      ``Add Mail Account``. After clicking ``OK`` you should be
      presented with a configuration window that lets you specify
      incoming and outgoing mail settings. Click the drop down menu
      for incoming and select ``POP3``. Set the POP3 server hostname
      to ``127.0.0.1`` and set the POP3 port to 2524. Next set the
      SMTP hostname to ``127.0.0.1`` and the SMTP port number
      to 2525. Select ``None`` for both drop down menus that by
      default specify TLS is used.  Set POP3 authentication to
      ``Normal Password`` and SMTP authentication to ``No
      Authentication``. POP3 authentication username must be set to
      ``alice@playground`` where ``alice`` is replaced with your username
      that you registered with. The password can be set to anything.


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
