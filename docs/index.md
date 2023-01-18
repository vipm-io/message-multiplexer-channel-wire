# Multiplexed Messenger Channel (MessengerM)

MessengerM represents multiple Messenger sub-Channels with one wire.

[IMAGE]

The Multiplexed Messenger Channel is similar to the Messenger Channel in that it is a multi-writer, multi-reader queue, but it is actually an array of such queues.

The endpoints have a full complement of optional inputs and outputs, but the new input that makes this Channel special is the subchannel index.  Different writers and readers can dynamically choose which subchannel they wish to communicate on.

So, where might this be useful?

## Manager-Minion Example

[IMAGE]

The Manager-Minion example has a manager VI which controls 8 concurrent station VIs (pardon my primitive UI, but that’s not the point of the example; imagine a much nicer UI).

* LEDs show the status of each station.
* The operator can select a station, select a command, and then send it to the station.
* The diagram has the familiar UI event loop, message handling loop (this time 8 of them), and a status display loop (which exits when it detects all stations have exited).
* The connection from the manager to the stations is a Multiplexed Messenger Channel so the manager can direct a command to a specific station using the assigned subchannel.
* The replies from all the stations are merged into a single Messenger channel for display.

Caveat: exit event should send exit to stations that haven’t exited yet (no harm as is).

## Reentrant Station VI

[IMAGE]

* Continue processing in the Active state until an error is detected or a command is received
* Exit the state diagram loop when the exit command is received
* Read commands on the assigned subchannel

A State Diagram defines the behavior of a Station (note “wizard locked” elements; just a pasted picture of the state diagram as documentation).

A station is in the Off state until it gets a start command.  At that point it goes to the Active state where it does its continuous processing until an error occurs or a command to Pause, Stop, or Exit is received.  From the Error state, a reset command will put it back in the Off state where it can be restarted if and when desired.

**The main thing to notice is that the station reads from its assigned subchannel.  It also includes the assigned subchannel in its status message so the manager can identify the sender.