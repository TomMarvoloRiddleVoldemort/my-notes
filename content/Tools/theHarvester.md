**theHarvester** is used to gather **open source intelligence (OSINT)** on a company or domain. theHarvester ==gathers emails, subdomains, hosts, employee names, open ports and banners ==from different public sources like search engines, PGP key servers and SHODAN computer database.

## Run theHarvester against a target
To view all the commands option, type:

`theHarvester -h`

Let's perform a full harvest on this target:

`theHarvester -d certifiedhacker.com -l 300 -b all`

On the `help` command you can see the meaning of these options, like `-d` stands for domain, and `-l` for limit the number of search results, and `-b` is the search engine/source.

theHarvester may return too much information to go through, for better readability, you can write the output to an HTML file:

`theHarvester -d certifiedhacker.com -l 300 -b all -f report`

The file will be exported in your home folder in Kali Machine.

Note: If you having trouble to export the HTML file, keep in mind it's a huge amount of information being collected, you can reduce the search engines/sources, instead to use them all at once.

***NOTE**:
Do scan 2 time as it can show less results 1st time.


# Scans


[[IP Address]]
[[Email Address]]
[[Subdomain Takeover]]
[[DNSLookup]]