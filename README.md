# Firewall iptables 
The script provided here has to purpose to block countries for which you do not want to offer online services.
The reason why it is advisable to do that is security.
A new server will approximaltely get scanned for open ports and vulnarabilites within 15 minutes.
And most of the scans are coming from countriees with which you will likely never have a deal.

That of course depends very much on the type of your business. 
Imagine an onlineshop or a service that you offer. Usually you will not get orders from China or Belarus.
However, analysing the failed logins of the server it is very likely that failed logins will come from those countries.
This traffic is only from hackers to see if there are open ports, and what services can be attacked.
In most cases if your server got hacked, you will never realize it. 
They will copy data which can be of use for them, remove all traces and disappear.

Now how nice is it, to be invisible for such countries.
Your server will simply not be available for hackers from those countries.
Even if your server was visible before, after that it will disappear from the list as being offline 
or not available anymore.

## Notes
### No protection against specific attacks
However, be aware it is a protection against bots, but not against a specific attack.
A hacker knows how to change the IP address. So once the server is attacked, this will not protect you.
It is an additional security measure to get from the automatically generated list for hackers from a lot of countries.
### Perfomance
If the list is very long (sample has a size of 5,2 MB), it can reduce the network perfomance, taking longer for a response.
Whitelist entries being at top of the list can help with that. So if you are serving specific countries, you 
can add whitelist entries. If found at the top of the list, the iptable scan will break and accept the request, instead of parsing the full list.

## Improvements
I am currently looking for improvements for the script.
How can I define IP ranges instead of a network mask to improve the perfomance.
And should some changes made to improve general security.

## Files
### firewall_iptables.sh
The file firewall_iptables.sh contains the iptable commands to block IP masks from specific countries.
Each area has an echo command to print the country for which the entries will be done.
It contains also a shell function to measure time. In small servers it can take a while for the script to run.
### defaultblacklist.txt
This file contains the list of countries with country code.
That are all countries from which you can expect hacking attacks, but usually not a deal.
It has no technical impact. Just a list of the countries that are handled in the firewall_iptables.sh script.


