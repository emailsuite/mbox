# mbox
Work with various MBOX file formats

## About format
All messages in an mbox mailbox are concatenated and stored as plain text in a single file. Each message starts with the four characters "From".

## There is a few standarts: mboxo, mboxrd, mboxcl, and mboxcl2




# More about mbox
The original mbox format (mboxo) only quotes From_lines, not quoted From_ lines. It is rarely used now.

mboxcl is mboxo, but with a Content-Length field in the From_line, which provides the number of bytes in the message. It is rarely used, either.

mboxcl2 is mboxcl without any From_ line quoting in messages (since the content length is given). It is used in a few Unix MUAs.

MMDF is an mbox-like format that uses neither From_ lines or trailing blank lines, but instead surrounds each message with four Control-As (^A^A^A^A). pine also supports this format.

The Eudora mail reader uses mbox as described in the previous section but does not add blank lines to the end of messages. It also uses the string ???@??? instead of the sender’s address in From_ lines.

Netscape uses mbox format, including blank lines, but uses “-” in place of the sender’s address in From_ lines.

