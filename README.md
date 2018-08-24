## Survey Data on M-Turk

In recent weeks, serious concerns have been raised about survey data collected on MTurk. People are concerned that a non-trivial proportion of respondents are not serious. And that at least some of them use bots to assist them with their answers. (This last bit is ironic: bots posing as humans on a platform whose name harks a scam where humans posed as bots.) Much of the evidence mustered about the concern is circumstantial, for instance, same responses to open-ended questions.

In response to the concern, I analyzed some recently collected data on MTurk. I focused on answering two basic questions: 

1. Even when we limit M-Turk HIT to US respondents only, how many of the IPs from which people fill out surveys are from non-US countries?  

2.  How many of the responses are submitted from blacklisted IPs?

To answer the questions, I leveraged [know your IP](https://github.com/themains/know_your_ip), a software that I had co-developed for another purpose: quickly getting metadata on problematic IPs when analyzing cybersecurity threats. The software provides simple hooks to multiple services that impute the lat/long of an IP, and let you know if an IP is part of one of many blacklists.

Of the 2,000 responses, Qualtrics could only get IPs for 1991. (I consider rest of 9 suspicious.) Of the 1991, 1886 are in the US. Of the 105 outside the US, 42 are from Venezuela and 17 from India. My sense is that these 105 respondents created MTurk accounts using US data---they have US credit cards or were once in the US---but are actually residents of another country. 

More shockingly, of the 1991 respondents, 321 are from blacklisted IPs. In all, there are 370 respondents who are either outside the US or have blacklisted IPs. And 9 whose IPs couldn't be recorded. In all, about 18.95% of the responses can't be trusted.

Suggestions for collecting and analyzing data from M-Turk surveys: 

1. Use Qualtrics country filter that uses its IP to lat/long to filter out respondents so that you don't get data from these respondents in the first place
2. Use [know your IP](https://github.com/themains/know_your_ip) to filter out other suspicious responses. 

And use checks recommended by others.

## Script and Data

* [Data](data/ip_metadata.csv)
* [Script](scripts/mturk.ipynb)

