# Sending emails with legitimate certs

Need i-whitelist yung IP address nung sender sa admin.google.com under **Apps** > **Gmail** > **Routing**

`apt install sendemail`
`apt install libio-socket-ssl-perl`
`apt install libnet-ssleay-perl`
`sendemail -t bayanielogada@gmail.com -s smtp-relay.gmail.com:587 -u Hello, friend -f notification@sandmansystems.com -m This is a test alert -o tls=yes -xu notification@sandmansystems.com -xp @sandman2013`

# Sending spoofed emails

* Make Namecheap account
* Add Namecheap email relay address targeted to the recipient
* Make sure Namecheap email relay address is random gibberish (dg231-6hd3-bnm3i@example.com)
* Add SPF ip4 record to DigitalOcean server
* Send the email to the relay address instead of the target recipient