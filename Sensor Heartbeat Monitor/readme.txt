Props to Mat at NotEnoughTech.com for the core code. I have used his and refactored for my purposes, which may be useful to some

A flow that monitors all your sensors. Depending on which timing category you place your sensor in, it will trigger an alert once a sensor doesn't respond within the group time.
You can use whatever alerting mechanism you wish. I use ntfy...
You will of course need to retrofit all your sensors instead of mine. The 'Context' -> 'Flow' display is invaluable for this to help you debug your system.
Dependencies:
* ntfy installed.

Arrays of important note:
* sensors - Contains all the sensors that are alive, along with a few relevant important methods.
* logs - a list of sensors that have dropped off the network (ie timed out)
