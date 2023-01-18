# Multiplexed Messenger Channel Wire for LabVIEW

The Multiplexed Messenger Channel Wire (MessengerM) represents multiple Messenger sub-Channels with one wire.

It is similar to the Messenger Channel in that it is a **multi-writer**, **multi-reader queue**; but it is actually **an array of such queues**.

The endpoints have a full complement of optional inputs and outputs, but the new input that makes this Channel special is the subchannel index.  Different writers and readers can dynamically choose which subchannel they wish to communicate on.

![MessengerM Write Read](docs/content/MessengerM%20Write%20Read.png)

This is useful in a variety of situations. [Click here to read more](docs/index.md).

Ready to give it a try?

## Getting Started

### Install the Package
Use [VIPM Desktop](https://www.vipm.io/desktop) (included with LabVIEW) to install [channels_messenger_multiplexed-0.1.0.2.vip](https://github.com/jimkring/labview-message-multiplexer-channel-wire/releases/download/v0.1/channels_messenger_multiplexed-0.1.0.2.vip)

#### Requirements

| LabVIEW | LV Bitness [32/64] | OS [Windows/macOS/Linux] |
|--|--|--|
|2019 or greater|any|any|

### Open the Examples

After installing the package, open the examples:

![Package Properties](docs/content/Package%20Properties.png)

Open and run the Main.vi

![Example Project](docs/content/Example%20Project.png)

### Use the Functions in the Palette

![Functions Palette](docs/content/Functions%20Palette.png)

## Keep Reading and Learn More

Read (and watch the short videos in) this great [Introduction to the Multiplexed Messenger Channel Wire](docs/index.md) document.