Activists organizations need to be light on their feet. While we may wish for our digital infrastructure to be open source, self sufficient, and self-hosted the reality is most orgs are lucky to get the basics in check.

Use the enemies' roads if you must.

Guerilla information warfare is about intelligently utilizing the best tools at hand, for cheap or free, with zero developer background.

# But First...

## Terms

Throughout this article you might see a few technical [terms](https://app.nuclino.com/t/b/73f091a8-b57f-4924-878f-1ec1b03fca10). I have attempted to keep everything as plain English as possible. Where there is a technical term I have tried to link a relevant article to explain the idea in plain English. If you have any further questions feel free to email me at jcklpe@protonmail.com

## Alternatives

This document is opinionated, meaning we only present as few options as possible and try to take a fairly clear stance on what the best tools for the job are. You should have the tools to not only use these tools but to find your own if you need to. Here are some websites you can use to learn about software alternatives.

- [Alternativeto.ne](https://alternativeto.net/)t
- [Capterra](https://www.capterra.com/)
- [Slant.co](https://www.slant.co/)
- [G2.com](https://www.g2.com/)

# Knowledge base

The starting point for any activist organization is their shared body of knowledge. A knowledge base is a system to help make that knowledge concrete and interlink it. Doing this is important because it allows information to propagate through the organization. It makes your organization robust and capable of adapting to new challenges. It increases your [bus factor](https://en.wikipedia.org/wiki/Bus_factor).

## Bottom Line Up Front

I would go with Nuclino unless your org members are used to using Notion and/or need it's more complex features. If you are interested in using Mediawiki, consider the costs of  [administration overhead](https://app.nuclino.com/t/b/bebf5774-5330-4f19-b376-47b07b825460).

### Mediawiki

Mediawiki is the [open source](https://opensource.com/resources/what-open-sourcehttps://opensource.com/resources/what-open-source) wiki Wikipedia is built with. A [wiki](https://en.wikipedia.org/wiki/Wiki) is simply a "collaboratively edited [hypertext](https://en.wikipedia.org/wiki/History_of_hypertext) document". Wikipedia is able to take in thousands of edits per second, many of them anonymous, from all over the world, and still maintain a fairly high level of accuracy because Mediawiki has a robust set of moderation tools. Every change made to Wikipedia is logged in a history, so if someone deletes important information or someone adds false information, moderators can go back and revert those changes. 

This is an important feature for large organizations. It means that control over content can be decentralized safely. 

Setting up and administrating a Mediawiki instance can be a bit of a tall order for this guerilla warfare approach. There are no free private Mediawiki instances out there. 

[You can install one](https://www.vultr.com/apps/mediawiki) with some basic webmaster knowledge on a Virtual Private Server for about 5 bucks a month, but administrating it can still be a challenge. 

### Nuclino

Nuclino is a free [closed-source](https://opensource.com/resources/what-open-source) private wiki. It has some features missing from the paid version (such as page history). They used to give a free standard account to non-profit and civic organizations but I'm not sure if they still do that. It's very straight forward and easy to use. 

### Notion

Notion is kinda like Nuclino on steroids. I prefer some things about Nuclino, but Notion has a lot of features that go well beyond the typical "wiki" feature set so it might be something you want to consider. Unlike Nuclino, the free version does have a page history feature, though it doesn't have any of the other more robust moderation tools that "real" wikis need to take advantage of that. 

# Chat

Chat apps are best for quick real-time communication between a small group of people.

Everyone uses chat already right? Yes, but not everyone uses secure chat options. Do not use any chat platforms owned by the large tech companies if you can help it. There are perfectly comparable, free, open source chat apps out there.  

## Bottom Line Up Front

Use Signal if you don't mind a phone number being attached to the account. Use Wire if you need to contact people without tying it to a phone number. Use Telegram if you need to coordinate a HUGE group of people, and complete security is not your priority. 

## Signal

Signal is an open source chat app. It's been recommended by Edward Snowden and the Electronic Frontier Foundation. It's [end to end](https://ssd.eff.org/en/glossary/end-end-encryption) (e2e) encrypted.  It has robust performance and UX. It can integrate with your normal SMS chat experience and be used on desktop. Signal is also the most widely used.

It does require you to create your account using your phone number. There are ways around this, but this is an inherent part of their [security model](https://ssd.eff.org/en/module/your-security-plan). 

## Wire

Wire is like Signal except it doesn't require a phone number to create an account. It does however keep metadata on it's servers. There's some trade off there. Generally you should go with Signal but Wire might be something to keep tabs on. 

## Telegram

Is a lot like these other two except it doesn't have e2e encryption for group messages. It only has e2e encryption for private messages. The big advantage of it is that you can have group messages with up to 75k members. That's a lot of people!

# Communications Platforms

Communications Platforms are more feature rich than chat apps and include functionality like threading, or channels, or more polished community moderation tools.

## Bottom Line Up Front

Use Slack for serious work, use Discord for casual stuff. Consider actually paying for a secure open source alternative like RocketChat. 

## Slack

Slack is not open source and the free version has strict limitations on how much of the chat history it can contain. That said, it is widely used and familiar to many people. Messages are not e2e and administrators can hypothetically access private messages between members without their consent and ultimately Slack can turn over anything written in Slack over to authorities.

## Discord

Discord is often called “Slack for Gamers”. It has channels similar to Slack. It lacks the threading feature. It has additional fun community oriented features like custom emojis. It's generally more casual and playful in it's design. It has a focus on voice and video chat and allows for “always on” voice chat rooms that people can casually drop in and out of on a whim.

This might be useful for a more diffused [affinity group](https://en.wikipedia.org/wiki/Affinity_group) but generally would not be recommended for serious work due to it's lack of features like message threading.

# Video

Video chat is useful for when you need face 2 face conversations, or when you're trying to hold a meeting with lots of people.

### Jitsi/ 8x8

Jitsi is the only open source option on this list. Video is a lot more bandwidth intensive so it's hard for open source projects to run free instances of their project for the general public to use.

The free Jitsi instance is owned by a company called [8x8](https://www.8x8.com/).

Jitsi is e2e and secure. Since you're not paying, using it for large conference calls can be hard.

If you are interested in supporting an open source platform co-op who is attempting to operate in this space, check out [meet.coop](https://org.meet.coop/)

### Zoom

Zoom is kind of the go to these days for most companies, in the same way that Skype used to be. Zoom has great performance, but [some serious criticisms](https://www.tomsguide.com/news/zoom-security-privacy-woes) have been made of it's security and free accounts can only hold meetings of 30 minutes or less.

### [Google Hangouts](https://hangouts.google.com/)

Google hangouts doesn't quite have the same performance as Zoom in my experience but it's free and doesn't have limitations and has pretty much the same feature set as Zoom. This would be my recommendation for orgs that are unable to spend any money.

### [Discord](https://discord.com/)

Discord has been mentioned as a community platform above. It can also be used for video conference calls. It's relatively secure, though like any free platform there will be performance issues sometimes.

## Streaming

Sometimes you don't need the communication to be 2 way, and you mostly just want to get your message out to people. In this case you might consider some of the following free streaming platforms. Some of the above video conferencing apps can also be used for streaming, such as Discord.

### [Facebook Live](https://blog.hubspot.com/marketing/facebook-live-guide)

Facebook Live is a good way to get out your information to a general audience.

### [Twitch](https://twitch.tv)

Twitch is another good alternative. Twitch originally had restrictions on what could be streamed. Originally it had to be video game related but now you can do more general talk and chat type content. Twitch is popular with a younger audience so it can be a good way to engage people who might otherwise not be super involved in your cause.

# Newsletters

Newsletters are an avenue to keep people engaged who are less involved with the day to day thing. Infrequent updates via email are flexible and low noise compared to social media, and also provide a path for people who might not have social media to stay in the loop. 

## Bottom Line Up Front

## Bottom Line Up Front

Use TinyLetter if you have less than 5k subscribers. Use Mail Chimp if you want to customize appearance and have less than 2k subscribers. Use Google Groups if you have more than 5k. 

### [TinyLetter](https://tinyletter.com/)

Free account has a 5k limit on subscribers. 

Enforces a simple visual design (this is probably best for activist orgs anyway though). 

### [Mail Chimp](https://mailchimp.com/)

Free account has a limit of 2k subscribers, and 10k emails sent monthly. 

2000 daily send limit

### [Send In Blue](https://www.sendinblue.com/)

GDPR compliant

based in France

Unlimited subscriber limit

9k monthly limit

300 a day limit

### [Google Groups](https://groups.google.com/)

This is a "[list serv](https://en.wikipedia.org/wiki/Electronic_mailing_list)" service, but can be used to send newsletters. 

# Public Relations

Use social media first and foremost due to [network effect](https://en.wikipedia.org/wiki/Network_effect). 

## Bottom Line Up Front

You know what social media is and what's out there. Hit up all the places that seem most appropriate to your cause and audience. Twitter, Facebook, Instagram, TikTok, Snapchat, Reddit, Discord (often treated as a form of social media), Twitch,  etc etc. The individual strategies for best maintaining these PR vehicles is outside the scope of this article but you can Google tips pretty easily. 

**Important Note:** Have a plan for how you will manage access privileges/passwords, and messaging strategy for these platforms! Make sure anyone who is given access understands what is okay and what is not okay to post, or how posts go through an approval process to be posted. And WRITE THESE RULES DOWN. Do not rely on everyone just being chill. You should set this stuff down in black and white, clearly defined, otherwise it can lead to A LOT of drama. 

**Important Note:** Obviously putting your stuff on these private platforms contains risks, both in terms of autonomy and security. You can try for a Wordpress website but a solution such as this will lack the network effect that social media provides. A federated open source account on [Mastodon](https://joinmastodon.org/) is a decent alternative, but social media platforms like this are much smaller and not used by "normal" people so their reach is limited. 

# Mass Text

I have less experience with this section so I really need someone to fill this stuff in. 

### [Action Network](https://www.actionnetwork.com/)

Action network is the only thing that does this that has a free tier level that I know of.

### [Nation Builder](https://nationbuilder.com/)

also supposed to be good

# Project Management

You need some kind of project management system. No matter how simple you think your work is, you should have a system where people can define goals, and then work towards achieving those goals. 

## Bottom Line Up Front

Use Trello for simple projects, use Notin if it's what you're using for knowledge base, use Github/Gitlab if you're doing anything code related. 

### [Trello](https://trello.com)

Trello is simple. It utilizes a project management framework called ["Kanban".](https://en.wikipedia.org/wiki/Kanban_board) Notion can also be used for Kanban, and if you already are using Notion for your knowledge management then you might consider that that of higher utility. 

### [Github](https://github.com/)/[Gitlab](https://about.gitlab.com/) issues

If you're doing anything code related you are probably already aware of these platforms and their ticketing software. It is a good idea to keep project management and the project it manages close to each other. 

# Graphic Design and Video

You're going to need to make images at some point, either for propaganda, social media, presentations, etc. Here's some free tools. 

### [Canva](https://www.canva.com/)

Canva is a graphic design platform. It makes it easy to do simple graphic design even if you don't have extensive graphic design skills. 

### [Photopea](https://www.photopea.com/)

Photopea is basically a free browser based Photoshop. It can be used to make more extensive photo and graphic edits. 

### [Adobe Spark](https://spark.adobe.com/)

Adobe Spark is a free graphic design and video suite that you can use to create and edit graphics on your phone. 

### [Lucid Charts](https://www.lucidchart.com/pages/)

Lucid Charts is a free diagram and chart making software. 

### [Draw.io](https://app.diagrams.net/)

Draw.io is similar to Lucid Charts but also open source. 

# Petitioning

### [Change.org](http://Change.org)

A general use petition platform. 

### [Coworker.org](http://Coworker.org)

Coworker is focused on workers trying to organize in their workplace for various causes, such as improved working conditions, better wages, unionization, or pressuring their company to address ethical issues. 

# Decision Making / Polling

Sometimes you need a structured digital way to make group decisions, and these apps can help. 

## Bottom line up Front

Use doodle for simple polls. Consider open source systems like Loomio or Decidim if you have more extensive needs. 

### [Loomio](https://www.loomio.org/dashboard)

Loomio is a really cool project based on the in person decision making process used during Occupy Wallstreet. It's open source, and there are no free hosted plans, you'll have to pay or run a self hosted instance yourself. 

### [Decidim](https://decidim.org/)

Another open source project, created for digital administration of municipal democracies. No free or paid hosted plans. Only available as a self-hosted project. Might not fit a small orgs needs but worth checking out. 

### [Doodle](https://doodle.com/free-poll)

Doodle makes simple polling easy. It's especially useful for when you need to get a bunch of people to schedule a time they're all available. 

# Email

Use whatever is easiest. Some advice would be to set up an admin account that all accounts are tied to. 

# Filesharing/Document Collaboration

Passing documents back and forth is not a good idea. It's messy and people very easily get out of sync with the latest version of the document. 

Holding copies of other kinds of files is similarly messy. Photoshop files for graphic design work, important documents in PDF, whatever it is, passing it back and forth by email is not a good solution. 

That's why it's better to host and work collaboratively in the cloud. 

For anything that's documentation or knowledge related: keep it in the knowledgebase/wikis mentioned above. For everything else, keep it in the cloud. 

### Bottom Line Up Front

Google Drive is basically the way to go.  Use NextCloud if you want an open source self hosted option. 

## Google Drive

You can do spreadsheets, slide presentations, documents, or just any other kind of file. There are size limits but they're pretty generous. Consider getting a G Suite subscription to get more space and better control access and management. 

## Nextcloud

Nextcloud is great though it can be a bit of a hassle to manage on your own. Consider getting it managed for you by a great coop like [collective.tools ](https://collective.tools/)

# Password/Credential Sharing

This is probably the single thing which orgs underestimate their need for. 

You have an organization built on organic social trust. But we use computers which rely on define security measures and protocols. Either you have the password for something or you don't either you are a moderator or administrator or you aren't. These things are defined in black and white, 1s and 0s. While the genesis of your org may be organic, it's best to put in a system for defining privileges and administrating them as early as possible. 

This is important for a few reasons: 

1. It increases your [bus factor](https://en.wikipedia.org/wiki/Bus_factor). If only one person has the keys to the kingdom, what happens if that person goes missing, gets burnt out, gets put in a coma, or leaves the org in some other way?
2. It helps to clearly define roles and permissions. Who is in charge of what and why? Right now everyone might trust Bobwith running all the administrative accounts but what if he has a falling out with other people in the org? Part of running a democratic org means defining these things clearly from the outset so they can be administrated with broad consensus and buy in. 

This is something you have to account for. Do not leave this to chance. 

### Bottom Line Up Front

Use Bitwarden. There are other options (such as Padloc, and Authpass) but I'm most familiar with Bitwarden and recommend them. 

## Bitwarden

Password managers do cost some money to get the group cloud syncing features but they're worth it and some of the most affordable paid apps on this list. Security isn't anything to cheap out on. 

Bitwarden family plan covers 6 people and costs 3.33 a month. 

# Scheduling

Having a public calendar is helpful. Google Calendar is the way to go. Use Doodle as mentioned above for scheduling specific meetings. Use Calendly for setting appointments with people. 
