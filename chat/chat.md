# Proposal: Select Rocket Chat as the chat recommendation for CIAB
---

## Motivation

As part of the Chapter In a Box project, we need a way for members to chat with each other in large groups. Many chapters use Slack, but Slack is closed-source, does not offer us control over our data, and charges sky-high fees for advanced features.  What do we need from our chat app? How can we fill this need as cheaply and easily as possible while protecting our member's data?

### What we need
* Channels for a large number of users to post in
* The ability to lock specified channels for announcements, or to admins only
* Private channels
* DMs
* Message threading - a crucial feature to help keep busy channels clean
* Simple sign up, for admins and users
* Easy to use mobile and desktop apps
* Federation to other instances running the same software so instances can easily collaborate
* Easy integration with video chat solution
* [not in Slack] - Encryption, to protect us from the people who want us to not be doing all this.
* [not in Slack] open source code, so we have transparency about what we're running, paying for, and storing member data with

## The Contenders
Given this list, there are a few open-source Slack alternatives I investigated:
* [Zulip](zulipchat.com)
* [Mattermost](mattermost.org)
* [Rocket Chat](rocket.chat)
* [Matrix.org](matrix.org)

Zulip and Mattermost do not offer federation or any kind of encryption. It has a lot of other positives but these two facts combined make them a non-starter. For other organizations or situations, these apps may work very well, but in our case they are not a good fit.

This leaves Rocket Chat and Matrix as the two viable options. Let's look at the pros and cons of each.

## Matrix
Matrix offers a lot of what we need - it's designed with federation and security in mind, it's totally open source with no paid plan at all, and it has a significant amount of energy behind it in the open source community.

### What is Matrix?
Let's first clarify what Matrix *is*: [Matrix.org](https://matrix.org/) is a project that publishes the Matrix standard for open, secure, decentralized, real-time communication. That's a mouthful. Matrix.org has a built a server for Matrix that can run their protocol, named Synapse. Synapse is the server software that handles all the messaging and whatnot. Riot is an example client implantation of the Matrix protocol and is available on all major devices.

However, Matrix is *not* a project run by nerds out of their basement - it's funded by millions of dollars from [New Vector](https://techcrunch.com/2020/05/21/automattic-pumps-4-6m-into-new-vector-to-help-grow-matrix-an-open-decentralized-comms-ecosystem/), a VC firm created by the founders of Matrix to help fund the project. Large users of Matrix are the French government, Mozilla, Wikipedia, KDE, and a few others. 

New Vector seems to be focusing on Matrix exclusively and everything involved in the project is open source. They also have a good relationship with Automattic, the company that owns WordPress, which we use as the CIAB CMS. They also note their monetization strategy looks like Wordpress' strategy, which is a good thing for us.

> The business model that we’re looking at with New Vector to go and drive — both to fund Matrix and also to keep the lights on and grow the projects and the company — is very, very similar to what Automattic have successfully done with WordPress.com - New Vector CEO/CTO and Matrix founder Matthew Hodgson

### The Good, The Meh, and the Bad of Matrix
Let's take a deep dive into Matrix, and see what would be great for us, what's not ideal, and what's bad about it.

#### The Good
* Matrix is out of beta and has the strongest security and privacy features available in any chat app on the market
* Built for decentralized yet secure servers - all servers whose users are participating in a conversation store a copy of the message so there is no one SPOF, and all messages are secured such that it's not easy for admins to just open a DB and read them as is the case with other options
* One-on-one VoIP/Video calling included*
* Integrates with 3rd party IdPs for free - **no other option has this**
* Riot makes it easy to join multiple Matrix servers - if we assume the entire org is on Matrix this makes collaboration very easy!

#### The Meh
* The UX of Riot is fine but not great.
* Matrix has not been out of beta very long and is still quite "rough around the edges" in a lot of ways. While Rocket Chat is also not as polished as Slack, Riot is a little worse in this regard.
* There is a comprehensive setup Ansible workbook that configures Synapse, Jitsi, and a lot of other helpful add-ons automatically, but...
* Community/room management tools are available, but in the fashion of open source they all need to be installed/configured/updated/secured and it's not terribly easy.

#### The Bad
* Matrix is a somewhat complex conceptually (look at the graphic on the homepage about reconciling messages), and Synapse in particular is complicated and difficult to set up for the first time. It's not as simple as SSHing into a box and pasting some commands as with all the other options. 
  * There is a docker container but that also comes with some caveats - I am investing to see if it's easier or just biting the bullet and running Ansible is.
  * **The difficulty of setup is by far my biggest concern with Matrix**
    * I don't think we can expect every chapter to have someone who has touched a command line before, let alone setup a reverse proxy or be familiar with Docker/Ansible, so setup must be as simple as possible or people will just give up and go back to Slack. 
    * I also don't think we have the resources to help chapters get setup with Matrix outside of guidance.
* There is a way to reply to messages in Riot, but it copies the message above the new message - this does not help reduce channel noise and arguably makes it worse
* VoIP/video calling doesn't appear to work super well right now and we would likely be better served with Jitsi anyway
* No Gluu support, as far as I can tell - it supports SAML but nobody has appeared to configure this yet. It was unclear and that's not a good sign to start with.

#### The Verdict
Matrix would easily be the top choice, but the difficulty of setup holds me back. I think orgs splitting, some using a technically great but complex option and some using Slack would be worse than most people using a technically-meh option. I am actively looking for ways to make setting up Synapse a snap, and if we can work out making installing/maintaining Matrix a snap I would recommend it easily. Until that time, Rocket Chat is an excellent contender.

## Rocket Chat
Rocket Chat is an open source program with a paid subscription component to enable advanced features. It's more directly comparable to Slack than Matrix is, and looks and works a little closer to Slack too. Rocket Chat features federated messaging, threads, and E2EE is in beta.

Rocket was started as an open-source project and has since raised a little more than [three million dollars](https://angel.co/company/rocket-chat/funding) in VC funding, along with however much they make from their paid plans. The main Rocket Chat products (the server, the apps) are all [open source](https://github.com/RocketChat). This checks all of our boxes for what we're looking for, so let's dive deeper.

### The Good, The Meh, and the Bad of Rocket Chat
#### The Good
* Rocket Chat is (nearly) fully functional across all major platforms
  * The mobile apps were rebased on React Native recently so a couple features are missing; the only ones we should be concerned with is accessibility and E2EE
* Easy to install (`sudo snap install rocketchat-server`) and configure
* Room management features to help control noise are included, among a bevy of others - I was pleasantly surprised by the amount of tools and connectors built in to Rocket Chat.
* Gluu has documentation on how to configure it with Rocket chat and it's easy.
* Jitsi integration is also available. You can choose to use the public Jitsi servers or point Rocket Chat at your own server.

#### The Meh
* Rocket Chat seems to have less energy behind it as an open-source project than Matrix - Rocket Chat seems to be more positioned as a chat system for enterprises that like FOSS because they can trust it and run it themselves. This isn't bad in my opinion but anytime a FOSS project is primary controlled by one company that presents a risk. 
* [Rocket Chat installs report analytics data, including location info, back to Rocket Chat HQ (see Usage Data)](https://rocket.chat/privacy)
  * Admins can turn this off - for now. Users can also turn off locations services in the mobile app to disable location data. 
  * The data is standard analytics data but this still presents a risk and we should ensure our instructions specify how to turn this off.
* The UX is similar enough to Slack it should be easy for people to figure out, but it's not very attractive.
* Performance can be an issue with more than 1k people on a server but with federation this should not be an issue

#### The Bad
* Threading is not as nice as Slack and introduces more channel noise.
* E2EE is new and not well-rounded yet
  * E2EE does not appear to cover media uploads - it only encrypts text (requires confirmation)
  * E2EE requires using a second password which is generated by Rocket Chat. I would not want anyone who doesn't have a password manager using E2EE. I assume if you lose this password you lose all your messages.
* I haven't tested federation - as it's more of an ancillary feature to Rocket Chat (rather than Matrix, which is designed with federation as a first principle) and I haven't been able to find much info on it running in the wild, I would want to test it before we rely on it.
* Less community support means less community plugins and fewer form posts to look at for help.

## Conclusion

### What's the best?
Matrix is a truly open source, community powered project built for federation and security. Unfortuantely, I believe Matrix is too complex to setup and secure for user inexperienced with tech, does not have some of the features we need, and therefore isn't currently feasible to recommend to chapters across the country.

**Rocket Chat checks almost all of our boxes for features, is open source (if not very community-powered), it works with our SSO pick, and is a `snap` to install.**

While Matrix is a solid contender I think Rocket Chat's ease of use will help us in the significant task of convincing hundreds of our comrades two switch off Slack - an option that is not only free to them but is also something they're familiar with and easy to administer and keep secure from trolls. 

**In my opinion, this task - convincing our comrades Slack is not a tenable long-term option because of security concerns and they should switch to an option that they will need to learn about and pay for - is the hardest task of this project.**

No matter what we pick, we will need significant change management resources (documentation, training sessions, FAQs, q+a with us, etc) to make the transition successful, which is why I weight ease of installation, ease of securing the server, the UX styling and other ease of use concerns so highly.

We are not an enterprise; we cannot push software to user's devices or create accounts for them; we do not have the volunteer hours to set up any chat server for every chapter (if they would even let us!); and especially during the COVID crisis chat is the most important tools chapters use to communicate. Splitting a chapter - either technically, by their admin goofing up their only method to communicate with each other - or culturally, by not having certain cohorts of users switch to Rocket Chat and petition to keep Slack, would be terrible.