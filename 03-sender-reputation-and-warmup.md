# Sender reputation and warmup

Once your mail is authenticated, providers judge you on reputation: a track record of how your mail has been received over time. A new sending domain or address has no reputation, which is its own problem, and an established one carries the weight of its history. Reputation is built slowly and damaged quickly, and most of it comes down to whether recipients have wanted your mail.

## What reputation is built from

Providers form a reputation for your sending domain and source based on signals they observe: how often recipients mark your mail as spam, how often you send to addresses that do not exist, whether recipients engage with or ignore your mail, and whether you hit spam-trap addresses that should never receive mail. Low complaints, valid recipients, real engagement, and no traps build a good reputation. The opposite erodes it. Crucially, this is tracked over time and per sending identity, so it is an asset you accumulate and can squander, not a fresh judgment on each send.

## The new-sender problem

A brand-new domain or sending address starts with no reputation, and providers are cautious with unknown senders because spammers constantly spin up new ones. If a new sender immediately blasts a large volume of mail, that pattern looks exactly like a spammer, and the mail gets filtered or blocked. This is why you cannot take a fresh domain and send to a large list on day one and expect the inbox. The lack of history is not neutral; combined with sudden volume, it is suspicious.

## Warming up

Warmup is the practice of starting small and increasing volume gradually, so the provider sees a normal, growing pattern from a sender whose mail is well received, rather than a sudden blast from a stranger. You begin by sending modest volumes to your most engaged recipients, the people most likely to open, reply, and not complain, which generates positive signals. As the provider observes good engagement and low complaints, you increase volume over days and weeks. This builds the track record that lets larger sends reach the inbox. Rushing warmup, or skipping it, is a common cause of a new sender's mail going straight to spam.

## Protecting an established reputation

A good reputation is valuable and worth protecting, because it is slow to rebuild once damaged. The fastest ways to damage it are a spike in spam complaints, sending to many invalid addresses, and a sudden unexplained change in volume or pattern. Sending consistently, to people who want your mail, at volumes that grow smoothly, preserves reputation. A single bad campaign, a purchased list, a misjudged send to disengaged recipients, can undo months of good standing, after which your previously inbox-bound mail starts landing in spam even for engaged recipients. Reputation is the compounding asset of email; guard it accordingly.

## Separate identities for separate purposes

Different kinds of mail carry different risk, and mixing them on one sending identity lets the riskiest drag down the rest. Transactional mail that people expect and engage with, like receipts and password resets, has strong signals; promotional mail to a broad list is riskier. Sending them from separate identities or subdomains keeps a problem with one from poisoning the reputation of the other, so that a rough marketing campaign does not send your password-reset emails to spam. As you grow, separating sending streams by purpose is a standard way to contain reputation risk.
