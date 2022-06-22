# mbox
Work with various MBOX file formats

## mboxo
```regex
From [\w\-\.]+@[\w\-\.]+ [a-z0-9]+
```
An original mbox format originated with Unix System V. Messages are stored in a single file, with each message beginning with a line containing “From SENDER DATE”. If “From ” (case-sensitive, with the space) occurs at the beginning of a line anywhere in the email, it is escaped with a greater-than sign (to “>From “). Lines already quoted as such, for example “>From ” or “>>>From ” are not quoted again, which leads to irrecoverable corruption of the message content.

## mboxrd
Named for Raul Dhesi in June 1995, though several people came up with the same idea around the same time. An issue with the mboxo format was that if the text “>From ” appeared in the body of an email (such as from a reply quote), it was not possible to distinguish this from the mailbox format’s quoted “>From “. mboxrd fixes this by always quoting already quoted “From ” lines (e.g. “>From “, “>>From “, “>>>From “, etc.) as well, so readers can just remove the first “>” character. This format is used by qmail and getmail (>=4.35.0).

## mboxcl
Originated with Unix System V Release 4 mail tools. It adds a Content-Length field which indicates the number of bytes in the message. This is used to determine message boundaries. It still quotes “From ” as the original mboxo format does (and not as mboxrd does it).

## mboxcl2
Like mboxcl but does away with the “From ” quoting. Dovecot uses this format internally.

## MMDF
(Multi-channel Memorandum Distribution Facility mailbox format) originated with the MMDF daemon. The format surrounds each message with lines containing four control-A’s. This eliminates the need to escape From: lines.
