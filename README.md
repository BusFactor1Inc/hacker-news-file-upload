Hacker News Upload (HNU)
------------------------

Upload a file to a Hacker News server.

Envinonment Variables:
---------------------

	HNU_user=<username> - Hacker News Server username
	
	HNU_pass=<password> - Hacker News Server password
	
	HNU_encoding=<encoding> - post encoding type, one of: none,
                             	  od-x, rot-13, morse-code, spoken-number

Usage:
-----

$ dd if=/dev/random of=file.bin bs=1k count=5

$ od -x file.bin > file.hex

$ ls -l file.*

-rw-r--r--  1 burton  admin   5120  3 Feb 14:30 file.bin
-rw-r--r--  1 burton  admin  23688  3 Feb 14:30 file.hex

$ export HNU_USER=<your Hacker News Server username>
$ export HNU_PASS=<your Hacker News Server password>

$ hacker-news-upload file.bin

Publishing:
Uploading: file.bin [0/2]
Uploading: file.bin [1/2]
Uploading: file.bin [2/2]

Meta-information:
Encoding: bin

$ hnu file.hex

Publishing:
file.hex [0/5]
file.hex [1/5]
file.hex [2/5]
file.hex [3/5]
file.hex [4/5]
file.hex [5/5]
Encoding: bin

$ HNU_ENCODING=od-x hnu file.bin

Publishing:
file.bin [0/5]
file.hex [1/5]
file.hex [2/5]
file.hex [3/5]
file.hex [4/5]
file.hex [5/5]
Encoding: od-x


Meta-information file:
----------------------

Encoding: [none | od-x | rot-13 | morse-code | spoken-number]

Future:
-------

0) Allows chunking.

Breaks encoded posts into <2kb post sizes and posts over multiple
stories using the following format:

It will post ([post size in bytes]/2000 + 1) MINIMUM stories for
binary encoding based on file size.

1) Pluggable encoders and decoders.

   - od-x => octal text encoding
   
   - rot13 => rot13 text encoding
   
   - morse-code -> morse code encoding
   
   - spoken-number -> encode as a large spoken number

--

Burton Samograd

2018

