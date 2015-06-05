# Internet of Things Nmap Fingerprints

A repository of Nmap scans for various IoT devices. The following command was run to perform the scan:

	nmap -n -Pn -sS -pT:0-65535 -v -A -oX <name> <ip>

Where **name** is a descriptive name for the device (ex: "wink-hub") and **ip** is the IP address the device has on your local network.

The above command should complete within an hour but it doesn't check for any UDP services that the device may be running. To perform a complete scan of the device that checks both TCP and UDP, please run the following command:

	nmap -n -Pn -sSU -pT:0-65535,U:0-65535 -v -A -oX <name> <ip>

If you're on an IPv6 network also try running the following command to get a fingerprint of its IPv6 capabilities:

	nmap -6 -n -Pn -sSU -pT:0-65535,U:0-65535 -v -A -oX <name> <ip>

To have your Nmap scan results added to this repository either submit a pull request or send your XML file to support@shodan.io
