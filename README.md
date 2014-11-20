CPres
=====

Presentation Software built on node-webkit, Zurb Foundation 5 and reveal.js being developed in my spare time for my own uses. Microsoft Powerpoint has fallen short of my needs for years and LibreOffice Impress no longer meets my requirements, either. After looking around in attempts to find a presentation program that supports multi-window and multi-monitors I've decided to make my own. Found myself in need of driving several displays 2-5 over the years. With each display showing unique content, sometimes all the same content and some presentations require a every changing mix of unique and mirrored content. The horrid workarounds I've come up with over the years have inspired me to make a tool that supports what I need natively without the worrying about if my workarounds will work on game day. Feel free to use it yourself, copy, modify, contribute or not. :)

* [Status](#current-status)
* [Contributing](#contributing)
* [Goals](#goals)
* [Window Types](#window-types)
* [CPres Format](#cpres-format)

## Contributing
Are you a looking to contribute some code? I'd love the help!
* Open a pull request with your changes, following the [guidelines](CONTRIBUTING.md).
* Please follow the above guidelines for your pull request(s) to be accepted.

## Goals

**Short term:**

* Multiple monitor aware.
* Multiple window support. Three types 1(max) master, 1(max) controller and any number of viewer windows.
* Basic editor for creation, saving and loading presentations from .cpres files. Files will likely be JSON or YAML formats.
 
**Long term or, if you prefer, The Wishlist:**

* Full editor for creation, saving and loading presentations.
* Remote clients. Clients can be a controller or viewer. Each CPres file can specify a Pre-Shared Key to determine what a client has access to.
* Full-offline support. No need for a remote webserver as it is built right into CPres so even without a Internet connection there is nothing to worry about. Just hook up a dedicate access point with DHCP for remote clients to connect too! Can't help you if you intentionally link Internet-based content into presentations, though.

## Current Status

Research with some experimenting to come up with a plan and mock-up to move forward with. Code commit activity will be non-existent for a while longer. Seems silly to commit anything when the real work hasn't even started and I'm just playing around with node-webkit. Current experiments say node-webkit offers everything I need or will need with the added benefit of changing/disable a few things to switch completely to a web browser.

## Window Types

**Master**  
Hidden window that, currently, doesn't do anything except launch the controller window. Only necessary because my current experiments with node-webkit indicate that *any* javascript error will force "crash" (force navigate to an error page) the main node-webkit window. There doesn't seem to be any graceful way to catch those errors either. Hence, the master window was born.

**Controller**  
Originally this was the master window and currently handles everything. From creating, loading and saving .cpres files to managing number of viewer windows, their locations and sizes.

**Viewer**  
These windows are bossed around. They do what the controller window or remote controller client tell them to do. Be here, go there, show this or whatever you want. What is on these windows is also what remote clients will see depending on what their Pre-Shared Key will allow.
