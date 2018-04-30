+++
title = "Periodic Table"
weight = 0
date = 2018-02-04T16:09:20-05:00

[menu.main]
Name = "Periodic Table"
parent = "Projects"
+++

## About

I am making a physical periodic table of elements with each element represented by a mechanical keyswitch. Element information is displayed on a screen mounted on the periodic table.

The whole system will run on a Raspberry Pi which will run the webview and act as a host for the switches as a 'USB keyboard'.

## Web Interface

I am making the display for this using React. The webpage will display the info for one element at a time. When each key on the table is pressed, the page will switch to show info about that element. The 118 elements will be mapped to a key event that the page listens for.

Here's a very early screenshot of the details for Hydrogen

![WIP web interface](/img/webview.png)

The data has been scraped from various sources online.

## Physical Table

I am making the physical table in the same manner people create custom keyboards. See [r/mechanicalkeyboards](https://reddit.com/r/mechanicalkeyboards) for more stuff like that.

I bought enough of these keyswitches (Gateron Blue) for each element.

![keyswitches](/img/keyswitch.jpg)

The are wired in a matrix and connected to a microcontroller. I will be using a Teensy++ 2.0. The microcontroller is flashed with a configured version of the [TMK keyboard firmware](https://github.com/tmk/tmk_keyboard) 

I designed the layout using [keyboard-layout-editor.com](http://www.keyboard-layout-editor.com/) and created CAD files for laser cutting the mounting plate using [builder.swillkb.com](http://builder.swillkb.com/)

![keyswitches](/img/layout.png)
![keyswitches](/img/cad.png)

I am going to try to get this laser cut at my university soon.

That's where the project currently stands. I've got other stuff being delivered soon and will continue working on the web interface in the meantime.