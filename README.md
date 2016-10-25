flume-syslogzip-source
=================

Apache Flume Syslog Source plugin for Syslog compressed messages

From Rsyslog Action module: The Action object describe what is to be done with
a message. Remote machine fordwarding compression facitlity:

z<number>

Enable zlib-compression for the message. The <number> is the compression level.
It can be 1 (lowest gain, lowest CPU overhead) to 9 (maximum compression,
highest CPU overhead). The level can also be 0, which means “no compression”.
If given, the “z” option is ignored. So this does not make an awful lot of
sense. There is hardly a difference between level 1 and 9 for typical syslog
messages. You can expect a compression gain between 0% and 30% for typical
messages. Very chatty messages may compress up to 50%, but this is seldom seen
with typically traffic. Please note that rsyslogd checks the compression gain.
Messages with 60 bytes or less will never be compressed. This is because
compression gain is pretty unlikely and we prefer to save CPU cycles. Messages
over that size are always compressed. However, it is checked if there is a gain
in compression and only if there is, the compressed message is transmitted.
Otherwise, the uncompressed messages is transmitted. This saves the receiver
CPU cycles for decompression. It also prevents small message to actually become
larger in compressed form.
