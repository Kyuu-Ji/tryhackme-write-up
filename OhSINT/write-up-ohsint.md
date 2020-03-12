# OhSINT

This is the write-up for the challenge OhSINT.
This challenge provides one downloadable file that is called _WindowsXP.jpg_.

## Challenge

As the name of the challenge suggests, this is an **OSINT (Open-Source Intelligence)** task.

### Questions

1. What is this users avatar of?
2. What city is this person in?
3. Whats the SSID of the WAP he connected to?
4. What is his personal email address?
5. What site did you find his email address on?
6. Where has he gone on holiday?
7. What is this persons password?

## Solution

Because it is an OSINT task, I will look into the metadata of the image file with **exiftool**:

![Metadata of image](/OhSINT/ohsint_metadata.png)

Now we get the author name that can be used to gather more information.
Using Google to look up that name, we get three interesting results:
- Twitter page: https://twitter.com/owoodflint?lang=en
- WordPress blog: https://oliverwoodflint.wordpress.com/author/owoodflint/
- GitHub page: https://github.com/OWoodfl1nt/people_finder

On Twitter he has a avatar that answers _Question 1_.
There is also one tweet, where he reveals a _BSSID_ that he can reach from his house.
With this information, it is possible to look up the _BSSID_ on **WiGLE** to locate him and find out the _SSID_ of that access point.

On GitHub he reveals his email address in the one repository he has.

On the WordPress blog there is one article in which he writes where he is right now.
The source code of that page also contains a weird string that is probably a password.
