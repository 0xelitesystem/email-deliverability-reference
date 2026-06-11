# Authentication: SPF, DKIM, DMARC

Before a provider will trust your mail, it needs to know the mail is really from you and not a forgery using your name. Three standards, set up as records in your domain's DNS, let you prove that. They are the price of entry for deliverability: without them, modern providers treat your mail with suspicion or reject it, and with them, you have cleared the first hurdle. This is the configuration part of deliverability, and it is worth getting exactly right.

## SPF: who is allowed to send

SPF, the Sender Policy Framework, is a published list of the mail servers authorized to send email for your domain. You add a DNS record naming the services allowed to send as you, your email provider, your newsletter tool, anything that sends on your behalf. When a receiving server gets mail claiming to be from your domain, it checks whether the sending server is on your list. If a server not on the list sends as you, that is a sign of forgery. The common mistakes are forgetting to include a service you actually use, which causes legitimate mail to fail, and exceeding the limits on how the record can be structured.

## DKIM: a signature proving integrity

DKIM, DomainKeys Identified Mail, attaches a cryptographic signature to each message, tied to your domain through a public key you publish in DNS. The receiving server uses that key to verify the signature, confirming both that the message genuinely came from your domain and that it was not altered in transit. Where SPF checks the sending server, DKIM checks the message itself. Together they establish that the mail is authentically from you and intact. Your email service usually generates the key and tells you the DNS record to publish; the work is publishing it correctly and keeping it in place.

## DMARC: the policy that ties it together

DMARC builds on SPF and DKIM by letting you publish a policy that tells receiving servers what to do with mail that claims to be from your domain but fails authentication. You can ask them to do nothing, to quarantine such mail to spam, or to reject it outright. DMARC also lets you receive reports on who is sending mail as your domain, which surfaces both forgery attempts and your own misconfigured services. A DMARC policy is what turns SPF and DKIM from checks into enforcement, and it is increasingly expected by major providers, especially for senders mailing many recipients.

## Get it right before you send volume

These records have to be correct before you send at any scale, because authentication failures are among the fastest ways to land in spam or get blocked. The order that works is to set up SPF and DKIM for every service that sends as you, confirm they pass, then add a DMARC policy starting in the do-nothing reporting mode to see what is happening, and tighten it to quarantine or reject once you have confirmed your legitimate mail authenticates cleanly. Tightening DMARC before your own mail passes will send your own messages to spam. The dns-email-authentication reference in this portfolio covers the records in more depth; the point here is that authentication is the non-negotiable foundation everything else sits on.
