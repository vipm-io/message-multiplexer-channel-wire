# Multiplexed Messenger Channel Wire for LabVIEW

The Multiplexed Messenger Channel Wire (MessengerM) represents multiple Messenger sub-Channels with one wire.

It is similar to the Messenger Channel in that it is a **multi-writer**, **multi-reader queue**; but it is actually **an array of such queues**.

The endpoints have a full complement of optional inputs and outputs, but the new input that makes this Channel special is the subchannel index.  Different writers and readers can dynamically choose which subchannel they wish to communicate on.

![MessengerM Write Read](docs/content/MessengerM%20Write%20Read.png)

This is useful in a variety of situations. [Click here to read more](docs/index.md)...

## Installation

[To Do]

## Getting Started

[To Do]

