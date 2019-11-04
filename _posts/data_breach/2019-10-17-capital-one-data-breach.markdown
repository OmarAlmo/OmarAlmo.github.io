---
layout: post
title: Capital One Data Breach
date: 2019-10-18 00:00:59 -0400
categories: [data-breach,security]
featured-img: saupload_capital-one-bank
permalink: category/:categories/:title
---

#### Summary:

Between March and April of 2019, Paige Thompson access unauthorized servers belonging to Capital One Financial Corporation. Capital One (CO) is a company that issues credit cards, loans, and provides other financial services. In the attack, Thompson obtained access to names, addresses, phone numbers, emails, dates of birth, and Social Security Numbers (SSN) and Social Insurance Numbers (SIN) of approximately 100 million Americans, and 6 million Canadians. The attack was carried out by getting access to database servers of CO and execurting 3 different commands. She was caught and criminally charged. This report is a detailed summary of the important events that occurred.

#### About the attack:

July 17th, Capital One received an email from an unknown person, stating that there seems to be private data on someone’s GitHub. Here, Capital One examined the GitHub account and found more than 700 files of company data, and IP addresses of specific servers. In addition, the files was timestamped April 21st, approximately two months before the email was received.

The commands were able to be executed at Capital One servers due to a server misconfiguration, which is one of the more common misconfigurations that is known by security researchers, as reported by UpGuard (a cybersecurity services firm). The commands executed by the attacker are...

1. Obtains security credentials for a particular account, this allowed the access to Capital One buckets. 
2. Lists all the names of folders in the storage space. 
3. Syncs and copy all the data.

The first step Capital One did after learning of this was to test out those commands, and the results turned out positive. That it did in fact function to obtain private data and extract them. Then, Capital One compared the 700+ files with their tested files and were able to confirm that it is also a match. To further investigate, the server command log files reflected the fact that the commands were executed on April 21st which matched the timestamp on the leaked files. The primary data copied was related to credit card applications, which some included SSN and SIN, although they were encrypted, other information such as names, addresses, dates of birth were not. Furthermore, of this data, Capital One estimates approximately 120 thousand SSN and 77 thousand bank account numbers were obtained.

Capital One later started tracing IP addresses found on their logs, and it showed number of connections and attempted connections using the same method (through the server misconfiguration) that came from various IP addresses including: TOR exit nodes, and specific IP addresses that began with 46.246. This beginning of this address belongs to IPredator, a Virtual Private Network (VPN) provider that is based in Sweden. The other connections came from The Onion Router (TOR) exit nodes; TOR is an anonymity tool used to conceal a user’s IP address, origin on connection and other identities. It bounces communication through several intermediate nodes, each in encrypted and with all this together, it is able to achieve this level of anonymity.

The GitHub account associated with the leak included Paige Thompson’s full name, and resume. More information about Paige Thompson, the attacker, is provided below. Furthermore, open research by the FBI agent in charge located a Meetup group that is hosted by Paige Thomson, or alias “Erratic”, and this Meetup also has a Slack channel. On June 26th and 27th, Thompson was openly active in posting various file names from the stolen files in the slack group. On July 4th, Thompson again posted a message asking for help about one of the stolen data. For the next few weeks, Thompson was active on her social media account, of which some had users name “Erratic”, with this information and some of her posts the FBI was able to cross reference images posted on her social media accounts and slack to conclude she is the attacker. Further, her twitter account contacted Capital One on June 18th with a message of her admitting to having data and “dropping” it first.

Finally, on July 26th, the FBI agent obtained a search warrant and on the 29th raided Paige Thompsons residence, arrested her and seized electrons for further evidence.

#### Damage of the Attack:

The final result of the attack is the leak of 100 million Americans, and 6 million Canadians personal information. Fortunately, the authorities and Capital One believe that the data so far was not used for any fraudulent or criminal activities. As well, the attacker stated to the investigators that she did not sell or share the data.

####About the Attacker:
Paige Thompson, is a former Amazon employee who worked as a systems’ engineer. Her previous experiences were all related to software and system engineering, systems architecture, and systems administrator. Her nickname as well that is used throughout her social media accounts and GitHub is “Erratic”. This helped the investigators to further connect the dots, as she was very active on some platforms such as Slack and Twitter. Nonetheless, the attacker was very careless to talk openly about her activities on twitter and tweeting about finding various data on Amazon servers, and her techniques. Thompson’s ultimate goal to attack Capital One is not entirely known, however she was arrested by the authorities on July 29th, less than a month after the initial tip to Capital One. Her charge was of computer fraud and abuse for an intrusion on the stored data of Capital One Financial Corporation.

#### Discussion:

There are a few mechanisms that could have prevented this breach. Firstly, the server misconfiguration that allowed is, is very common. Thus, a third-party examination of their servers would have greatly helped, thus is fairly possible by the IT department. As well, Capital One could have implemented a mechanism that is trigger if some commands are executed, as mentioned above, the logs showed that the certain commands executed by the attacker were present. This is important for two main reasons: system integrity and data confidentiality. The data should only be accessed if it is needed with the proper authorization, and any execution to the servers should be verified. Again, this is fairly feasible.

What is also interesting about this incident is the timeline. The attacker had multiple access to the servers without any problems or the knowledge of Capital One beginning March 2019, and the attacker’s arrest was only 5 months after. Without the tip from the random person, the data could still be online or even worst used for fraudulent activities, by the attacker or by any person online since the data was there. As well, the tip came almost 2 months after the attack, meaning the data was online for anyone to see. This brings the question if Capital One is aware what activities is happening with their data internally with employees or externally.

<br/><br/><br/><br/>
Resources

> Brandom, R. (2019, July 31). The Capital One breach is more complicated than it looks. The Verge. Retrieved from https://www.theverge.com/2019/7/31/20748886capital-one-breach-hack-thompson-security-data

> Martini, J. (2019, July 29). Thompson Complaint. Retrieved from https://www.justice.gov/usao-wdwa/press-release/file/1188626/download

> Thorne, J. (2019, August 23). Capital One Hacking Suspect Paige Thompson Appears in Court, Ordered to Remain in Custody. Retrieved from https://www.geekwire.com/2019/capital-one-hacking-suspect-paige-thompson-appears-court-ordered-remain-custody/

> U.S Attorney's Office. (2019, July 29). Seattle Tech Worker Arrested for Data Theft Involving Large Financial Services Company. Retrieved from https://www.justice.gov/usao-wdwa/pr/seattle-tech-worker-arrested-data-theft-involving-large-financial-services-company

> UpGuard. (24 July 2019). How to Minimize Cyber Risk in Microsoft Environments. Retrieved from https://www.upguard.com/blog/minimizing-cyber-risk-in-microsoft-environments
