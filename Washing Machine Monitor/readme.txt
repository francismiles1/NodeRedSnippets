Props to Mat at NotEnoughTech.com for the core code. I have used his and refactored for my purposes, which may be useful to some

This is useful for those that have dumb washing machines, that either don't notify when complete or don't persistently remind you to empty. Like mine, resulting in the discovery of smelly clothes many days later!!
A flow that monitors your washing machine's current profile, and depending on the average current at the time, pulls the algorithm into specific states.
Clearly, a power sensing switch is required, I use pre-tasmota-flashed ones (Smart Plug) from Local Bytes.

Important Settings:
Please check the Settings module. This contains some important settings you will need to configure
* var standbyCurrent = {"LowLimit": 0.04, "HighLimit": 0.085 }; This needs configuring based on your washing machine's standby current. This is trial and error (it takes a while to get the perfect numbers, to eliminate false triggering), but you will get there.
* flow.set("MetricFrequency", 60); this MUST match your Smart Plug Logging Telemetry Period Figure. This generally defaults to 300, but I set mine to every 60 seconds. Setting it to 30 seconds is ok if you need more fine-grained accuracy but increases your MQTT traffic a little.

Dependencies:
* You can use whatever alerting mechanism you wish. I use ntfy...
