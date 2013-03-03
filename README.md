#mquery
Small python script for extracting headers from RFC2822 mailfolder files

#Use 
Currently supports two commandline paramters for querying raw hedaers (--hdr) or for extracting space separated e-mail addresses --addr

a sample query could look like `mquery 1333298923.tAX00Ka6d52557342.atlas --addr to,from`

##Example
The two examples below illustrates the difference between the addr and hdr parameters

    sondove@atlas:~/projects/mquery$ ./mquery /tmp/1333298923.tAX00Ka6d52557342.atlas --addr from,to
    sender@example.com receiver@example.com

    sondove@atlas:~/projects/mquery$ ./mquery /tmp/1333298923.tAX00Ka6d52557342.atlas --hdr from,to
    MR Sender <sender@example.com>
    "receiver@example.com" <receiver@example.com>
    
The `--hdr` command can be used to extract arbitrary headers from the file mail

    sondove@atlas:~/projects/mquery$ ./mquery /tmp/1333298923.tAX00Ka6d52557342.atlas --hdr content-type,return-path,mime-version,message-id
    text/plain; charset=us-ascii
    <sender@example.com>
    1.0 (Mac OS X Mail 6.0 \(1400\))
    <29X2G325-XFE2-829C-BK02-03AH298C32FA@example.com>
