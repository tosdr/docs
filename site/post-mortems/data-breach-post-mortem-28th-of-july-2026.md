# Data Breach Post-Mortem 28th of July, 2026

On the 28th of July 2026, at around 14:00 CET, we found a dump of our production database checked into GitHub, uploaded in 2018. After some hours, we checked inside the dump and found that it contained real user data. 370 users are affected, with their email, password hash and IP address being affected.

We understand 8 years is a long time to not catch this, the only reason we did is because we were approved in the Claude Cybersecurity program, and we scanned our repository Phoenix for issues, where it was flagged. It was in a stale branch, hence why it was not caught earlier. Never checked into Master.

Upon realizing the scale of the problem, we immediately reset all affected user passwords and contacted the Autoriteit Persoonsgegevens (the Dutch Data Protection Authority) as mandated by law. To protect our users and ensure the public exposure was fully resolved before drawing further attention to the incident, emails were sent to affected individuals after the file was permanently secured. Because the data had been publicly accessible over an eight-year period, we are unable to determine the precise extent of exposure during that time.

For transparency, here is a rough timeline of events:

28.07.2026 - 14:00 CET: Claude flagged the exposed credentials in the stale branch, the affected branch has been deleted.&#x20;

29.07.2026 - 16:42 CET: The Autoriteit Persoonsgegevens (NL) has been notified.&#x20;

30.07.2026 - 09:33 CET: We have made contact with GitHub to get the exposed credentials removed from caches and forks.&#x20;

15.08.2026: GitHub has removed all forks of Phoenix and emailed everyone that had forked us about the breach. Blob Caches have yet to be deleted.&#x20;

17.08.2026 - 11:13 CET: We have made the Repository edit.tosdr.org private to prevent further exposure, this resulted in a purge of the blob cache as well. The direct reference to the file came up with a 404 (Not Found).

We have also sent everyone affected the following mail:

```
Dear ToS;DR contributor,

We’re sorry to let you know that a subset of personal data, including yours, had been accidentally leaked on a development platform for edit.tosdr.org (also known as Phoenix). The data that was disclosed, while not directly readable or searchable, included the email address you used to contribute to edit.tosdr.org in 2018; IP addresses of your connections at the time, as well as a cryptographic hash of your password. This means that your password itself was not disclosed. However as a security measure, your account password has been reset on edit.tosdr.org to mitigate any attempts to sign in with previous credentials.

More details below or at: https://docs.tosdr.org/site-policy/post-mortems/data-breach-post-mortem-28th-of-july-2026

What you can do next:

We’ve already taken all steps available to us to mitigate this accidental leak as soon as we became aware of it (see further below for details). 
If you want to use Phoenix again, the system will ask you to set a new password for your account. There is nothing else required of you as such, and we’ve ensured removal of the leak from publicly available records that we were aware of. However as good measures of precaution we recommend the following:

- Review the passwords you use elsewhere to ensure that if you might have reused them, you should also reset your credentials where relevant
- Be careful and look out for phishing emails posing as ToS;DR. We will NEVER ask for your password. 

And of course the ToS;DR team remains fully available if you have any questions or need any assistance to help secure your account. You can send us a mail to team@tosdr.org for help.

Details of what happened:
On 28 July 2026, we used a new tool for scanning our codebases for security vulnerabilities, and it found that 8 years ago, a member of the development team accidentally disclosed a copy of our production database (as a “dump” file) to the publicly available source code repository at GitHub. This database dump notably contained details of 370 contributors to edit.tosdr.org including: email address of their account, alongside a hashed version of their password and the IP address used to connect. 
The reason it took so long to be found is because it was in a stale branch not part of the active development, so no one had it on their radar.

What we’ve done since discovery:
Since discovery on 28 July 2026, our initial actions have been to assess the extent of the leak and address it wherever we could to stop it. We’ve also immediately reset the impacted passwords.

Given the leak was first disclosed via GitHub, we’ve filed multiple security reports per their processes to purge the accidental leak from available repositories, including forks controlled by other users of GitHub not part of the ToS;DR team using take-down notices for exposed credentials. As far as our knowledge, they have all been removed.

As per our legal obligation, we've filed a report on this situation to the Autoriteit Persoonsgegevens, the Netherlands’ Data Protection Authority on 29 July. We’re following up with them as progress is being made.

We are looking at more ways to prevent this from happening again through automated scanning and pre-commit checks. You can follow this process along on our GitHub.

We really want to make sure this never happens again, and have published a public post-mortem (https://docs.tosdr.org/site-policy/post-mortems/data-breach-post-mortem-28th-of-july-2026) with the steps we are taking to make sure. We will continue to update that page as the situation develops if anything relevant comes up. 

We’re sincerely sorry for all this. While we believe this was an honest mistake by a well-intended contributor - whom we thank for many important contributions to the project - we wish we’d identified this error sooner. This isn’t the high standard we hold ourselves to, but ToS;DR remains a small and benevolent project run by volunteers around the world and we welcome good-faith contributors from all around the world regardless of background.
The current development team will continue its efforts to improve the security of our processes and help ensure this kind of event does not happen again. 

Feel free to email us at team@tosdr.org if you have any further questions.

the ToS;DR team
```

We were in contact with GitHub early on to request the removal of the affected data. However, their standard process included notifying all fork owners of the incident and providing specific details, including the branch name, filename, and commit hash.

Dump files are already ignored, and this has been standard procedure at ToS;DR for years; unfortunately, it was missed during early development cycles. In the future, we will be making sure all dump file formats, such as .dump, are added to .gitignore across all of our repositories that might be created in the future, and I will personally brief the entire development team to be more careful before pushing. Our systems were not affected and are still secure, we will do our best to protect your current data and make sure that it never gets released.

Thank you for reading, and we are sorry this happened.

Erik from ToS;DR
