---
layout: post
title:  "The Austrian Messenger Surveillance Act"
date:   2025-12-17 23:18:00 +0100
categories: posts
---


<h3>Chapter 1: Introduction</h3>

<p>
Recently, the Austrian government passed the Messenger Surveillance Act <span class="bibliography_nums">[1]</span>, a law that allows the country's domestic intelligence service to monitor digital communications in order to prevent terrorism and espionage. The law was debated in public and in parliament, with supporters arguing that it modernizes Austria's intelligence capabilities, while critics warned of potential risks to citizens' privacy <span class="bibliography_nums">[1]</span>.
</p>
<p>
Although, in theory, it is not permissible for the government to deploy spyware without legal approval <span class="bibliography_nums">[2]</span>, in practice, there are little checks and balances that actually ensure legitimate use of state-level spyware. Amongst other things, given the ephemeral nature and opaqueness of mercenary spyware deployments, it frequently operates in a grey zone where accountability is minimal and misuse can go undetected for long periods of time. In contrast, conventional abuses of power tend to leave a public trace. Warrantless raids, for example, can be observed by community members and brought to the attention of journalists. Warrantless digital raids can and will go unnoticed. This subtle difference makes spending taxpayers' money for mercenary spyware highly problematic.
</p>
<p>
The Austrian Messenger Surveillance Act prevents terrorism as much as the EU chat control proposal protects children from predators, and as much as the Patriot Act enhanced US national security. A classic anti-democratic fallacy. It allows anti-democratic surveillance methodologies to become part of a government's weapons arsenal with very little potential for public oversight.
</p>



<h3>Chapter 2: The Case of Spain et al.</h3>

<p>
A recent example of unlawful use of mercenary spyware within the EU can be found in Spain, where at least 63 elected officials of Catalonia's government and people supporting the Catalan political independence movement were targeted with NSO group's Pegasus spyware. Of the 63 confirmed targets, forensic analysis proved infections on 51 individuals' devices <span class="bibliography_nums">[3]</span>.
</p>

<p>
NSO Group says Pegasus is sold only to governments, so any use of it points to state involvement. While the surveillance operation against Catalan officials could not be linked to a specific government, reports that Spain is an NSO client and the fact that victims included Spanish members of the EU Parliament, Catalan presidents, and legislators, strongly suggests a connection to the Spanish government <span class="bibliography_nums">[3]</span>. In the case of Spain, many of the victims had not been accused of serious crimes, and most were neither criminals nor terrorists, the categories cited by surveillance firms to justify selling their spyware <span class="bibliography_nums">[3]</span>, and cited by governments to justify buying it. Similar to the Austrian proposal <span class="bibliography_nums">[2]</span>, Spain also requires formal approval and oversight by the judiciary and the relevant minister <span class="bibliography_nums">[3]</span>. Similar to Austria, Spain is a liberal democracy. And yet, clandestine surveillance of political figures, activists, and members of civil society proceeded for years.
</p>

<p>
Spain is not the only example. In 2025, it was revealed that the Italian government had actively deployed Paragon's Graphite spyware, at around the same time when the Citizen Lab forensically confirmed Paragon infections on the phones of multiple Italian civil society members and journalists. The targets had already received warning messages from Meta in 2024 that they had been targeted by “sophisticated hackers”. The Italian government's conflicting responses to these cases fuelled suspicion that it may have been directly involved in the operations <span class="bibliography_nums">[4]</span>.
</p>

<p>
Another scandal has unfolded in Greece involving the spyware Predator, developed by the Israeli company Intellexa. The software was allegedly used to target Greek judges, journalists, and politicians. As of the time of writing, the case has moved to court, where investigators are examining the role the Greek National Intelligence Service may have played in the unlawful surveillance <span class="bibliography_nums">[5]</span>.
</p>

<p>
And after all these scandals and years of abuses of spyware within the EU, the Austrian government decided that it was time to join the club.
</p>


<h3>Chapter 3: The Case of Austria</h3>

<p>
As of writing, the Austrian government is starting a two-year tender process to find a potential seller of mercenary spyware <span class="bibliography_nums">[6]</span>. So, how much does it cost for a small nation to purchase sophisticated spyware? The answer is: it depends on the number of planned infections. Some contracts are based on concurrent infections, meaning the clients pay per number of devices that can be simultaneously infected <span class="bibliography_nums">[7]</span>. For the Austrian government, and the estimated maximum number of 30 infections per year <span class="bibliography_nums">[2]</span>, this can actually be relatively cheap. However, this is not accounting for the upfront costs and recurring subscription-like costs to get hold of up-to-date exploits, which are millions of euros of taxpayer money.
</p>

<p>
Imagine having to develop exploits for dozens of different phones, running dozens of different versions of iOS or Android, and on top of that, running different versions of WhatsApp or Signal (some that may or may not have implemented fixes for certain backdoors). As a spyware company this means constantly maintaining exploits that may break at any update and only work on a small subset of targets, which is extremely costly. So, in the end, the government has a choice of investing in semi-dysfunctional spyware or an up-to-date allrounder which costs a fortune.
</p>

<p>
When it comes to functionality, Austria is seemingly opting for a more “restricted” type of spyware. More concretely, according to <span class="bibliography_nums">[2, §15b]</span>, only messages sent, transmitted or received within the scope and period of the authorization and only applications specified in the authorization can be monitored. The Austrian wish list is long: a timer-based kill-switch, selective monitoring of applications and chats, and the spyware must not yield the device dysfunctional in any way <span class="bibliography_nums">[8]</span>. It seems that to comply with the government bill, an off-the-shelf Pegasus would not suffice, and a highly-customized version of the spyware would need to be acquired. Interestingly, the Austrian government bill <span class="bibliography_nums">[8]</span> identifies Skype as an example of end-to-end encrypted communication that the Austrian government seeks to monitor potential terrorists, an app that has been retired before <span class="bibliography_nums">[8]</span> was even published, which proves how disconnected the drafters were from the actual state of modern tech.
</p>

<p>
The main flaw in Austria's messenger-surveillance proposal is the way lawmakers frame the technical scope of the monitoring. In the proposal, they try to reassure the public by claiming that authorities would only be capable of monitoring specific chats or messages, not extract other content from the device, and not interfere with other apps or system functions.
</p>

<p>
Although, Graphite, a spyware solution of Paragon, reportedly only targets messaging applications and does not fully compromise the device <span class="bibliography_nums">[4, 9]</span>, most sophisticated mercenary spyware, however, obtain high privileges (i.e., root-level access) to the devices, meaning that by default they have access to far more than just a specific messenger application. As <span class="bibliography_nums">[10]</span> correctly reaffirms, most mercenary spyware is too invasive to selectively target applications, let alone specific chat messages.
</p>

<p>
The mere existence of these tools in the hands of governments means that there is potential for invisible abuse. Short-sighted decision making can quickly turn the initial idea around with a simple change in the ruling party, which could present powerful mercenary spyware on a silver plate to a less democratic party.
</p>


<h3>Chapter 4: Prevention</h3>

<p>
In light of the fact that mercenary spyware is more misused than used, this chapter outlines some potential prevention approaches. In the end, it is about raising the costs of a successful exploit, to make it unaffordable for a small nation state like Austria to justify investing in such tools.
</p>

<h4>1. The bullet-proof approach</h4>
<p>
Don't use a phone.
</p>

<h4>2. The (relatively) bullet-proof approach</h4>

<p>
<b>Threat Model</b>: The proposed mitigation focuses exclusively on thwarting targeted, remotely initiated zero-click exploit-based attacks designed to compromise a mobile device and access sensitive cleartext data stored on the device. It does not address vulnerabilities in communication protocols that may be exploited in transit, potential side-channel information leaks, or methods for reducing the likelihood of location tracking. It does not consider scenarios in which an attacker obtains physical access to the device, nor does it cover supply-chain compromises or malicious hardware implants.
</p>

<p>
<b>Assumption</b>: You still want to have a functional mobile device with 5G access while on the move and you want to reduce your attack surface as much as possible. The following setup allows you to do this.
</p>

<p>
<b>Setup</b>:
</p>

<p>
<b>a)</b> a decoy device, with a registered SIM card under your name, logged into your Google/iCloud account, activated FaceTime and iMessage, activated SMS, WhatsApp and Telegram accounts linked to the phone number. These are all the accounts and pathways that will be used as attack vectors by mercenary spyware.
</p>

<p>
<b>b)</b> an operational device, running Graphene OS with heavily reduced attack surface. No SIM card, disabled Bluetooth. Only Wi-Fi should be functional. For 5G access, connect to the personal hotspot of the decoy device. Only connect the operational device to the decoy device when 5G access is needed. Disconnect it when not in use. Simple “worm-style” propagation by infecting the decoy device and then automatically pushing the exploit to the operational device over the hotspot is more difficult than just infecting the decoy device. Also, some exploits may not be persistent, meaning a simple reboot can yield them dysfunctional. Therefore, make sure to reboot the operational and the decoy device once per day.
</p>

<p>
<b>c)</b> adding a little bit of security through obscurity: use an unknown, custom messaging service, with practically no attack vector, as the only messaging app on the operational device. Mercenary spyware companies predominantly develop exploits for widely-used services like WhatsApp, Signal, iMessage, FaceTime, the iOS WebKit, Apple FindMy, etc.
</p>

<p>
The goal of this setup is to yield out-of-the-box exploits useless. Lateral movement over Wi-Fi onto a different device running a different OS is most likely not an out-of-the-box functionality. To turn network access into a full compromise usually requires chaining multiple other vulnerabilities together, after infecting the decoy device. This makes the exploit more costly and time-consuming. The spyware model that Austria and other small actors can afford to subscribe to won't include highly customized, sophisticated exploit chains.
</p>

<p>
Using a different OS has, amongst other things, the advantage that no ecosystem-proprietary services can help the attacker with lateral movement. For example, Apple ecosystem features such as AirDrop, Handoff, or account syncing stuff, could be leveraged to compromise the operational device via the decoy device. Incompatible OSes may prohibit this. For an attacker to discover the operational device without compromising the decoy device, they would need physical proximity to the device or prior knowledge about the custom messaging app service used on the operational device. Both of this is not part of the classic mercenary spyware threat (and business) model.
</p>


<h4>3. The better-than-nothing approach</h4>

<p>
If you have an iPhone, turn on Lockdown Mode. On Android devices, turn on Google's Advanced Protection. In some instances <span class="bibliography_nums">[11, 12, 13]</span>, Lockdown Mode has been proven to prevent certain spyware infections by the NSO group.
Use Signal as the only messaging app. Make sure to choose a Signal username that cannot be linked back to your name and in the Signal Settings under <i>Privacy->Phone Number</i> check <i>“Nobody”</i> under <i>“Who Can See My Number”</i> and <i>“Who Can Find Me By Number”</i>. This prevents people, who don't know your username to send messages to your Signal account using your phone number. Also, in <i>Settings->Chats</i> turn off <i>“Generate Link Previews”</i>.
</p>

<p>
Do not use WhatsApp, Telegram, SMS or Email. In addition, disable FaceTime and iMessage completely, as this greatly reduces the attack surface.
</p>


<h3> Bibliography </h3>
<p>

<span class="bibliography_nums">[1]</span>	Parlamentsdirektion and Nationalrat. "Messenger-Überwachung nimmt letzte parlamentarische Hürde." <a href="https://www.parlament.gv.at/aktuelles/pk/jahr_2025/pk0718">https://www.parlament.gv.at/aktuelles/pk/jahr_2025/pk0718</a> (accessed December 07, 2025).<br><br>

<span class="bibliography_nums">[2]</span>	Parlamentsdirektion and Nationalrat. "Regierungsvorlage: Bundesgesetz, mit dem das Staatsschutz- und Nachrichtendienst-Gesetz, das Sicherheitspolizeigesetz, das Telekommunikationsgesetz 2021, das Bundesverwaltungsgerichtsgesetz und das Richter- und Staatsanwaltschaftsdienstgesetz geändert werden." <a href="https://www.parlament.gv.at/dokument/XXVIII/I/136/fname_1693648.pdf">https://www.parlament.gv.at/dokument/XXVIII/I/136/fname_1693648.pdf</a> (accessed November 17, 2025).<br><br>

<span class="bibliography_nums">[3]</span>	J. Scott-Railton et al. "CatalanGate: Extensive Mercenary Spyware Operation against Catalans Using Pegasus and Candiru." The Citizen Lab. <a href="https://citizenlab.ca/2022/04/catalangate-extensive-mercenary-spyware-operation-against-catalans-using-pegasus-candiru/">https://citizenlab.ca/2022/04/catalangate-extensive-mercenary-spyware-operation-against-catalans-using-pegasus-candiru/</a> (accessed November 15, 2025).<br><br>

<span class="bibliography_nums">[4]</span>	B. Marczak et al. "Virtue or Vice? A First Look at Paragon's Proliferating Spyware Operations." The Citizen Lab. <a href="https://citizenlab.ca/2025/03/a-first-look-at-paragons-proliferating-spyware-operations/">https://citizenlab.ca/2025/03/a-first-look-at-paragons-proliferating-spyware-operations/</a> (accessed November 19, 2025).<br><br>

<span class="bibliography_nums">[5]</span>	K. Koukoumakas and K. Kallergis. "Phone spyware scandal in Greece moves to court as critics claim cover-up." BBC. <a href="https://www.bbc.com/news/articles/ced56p5l2wwo">https://www.bbc.com/news/articles/ced56p5l2wwo</a> (accessed November 19, 2025).<br><br>

<span class="bibliography_nums">[6]</span>	B. Steinbrenner. "Messenger-Überwachung: Worauf sich die Regierung geeinigt hat." Die Presse. <a href="https://www.diepresse.com/19807577/messenger-ueberwachung-worauf-sich-die-regierung-geeinigt-hat">https://www.diepresse.com/19807577/messenger-ueberwachung-worauf-sich-die-regierung-geeinigt-hat</a> (accessed November 17, 2025).<br><br>

<span class="bibliography_nums">[7]</span>	A. Bruce, J. Scott-Railton, and D. Knowles. "Exposing Pegasus: How the State Spies on You." The Citizen Lab. <a href="https://citizenlab.ca/2025/09/exposing-pegasus-how-the-state-spies-on-you/">https://citizenlab.ca/2025/09/exposing-pegasus-how-the-state-spies-on-you/</a> (accessed November 17, 2025).<br><br>

<span class="bibliography_nums">[8]</span>	Parlamentsdirektion and Nationalrat. "Erläuterungen: 136 der Beilagen XXVIII. GP - Regierungsvorlage." <a href="https://www.parlament.gv.at/dokument/XXVIII/I/136/fname_1693650.pdf">https://www.parlament.gv.at/dokument/XXVIII/I/136/fname_1693650.pdf</a> (accessed November 16, 2025).<br><br>

<span class="bibliography_nums">[9]</span>	T. Brewster. "Meet Paragon: An American-Funded, Super-Secretive Israeli Surveillance Startup That ‘Hacks WhatsApp And Signal'." Forbes. <a href="https://www.forbes.com/sites/thomasbrewster/2021/07/29/paragon-is-an-nso-competitor-and-an-american-funded-israeli-surveillance-startup-that-hacks-encrypted-apps-like-whatsapp-and-signal/">https://www.forbes.com/sites/thomasbrewster/2021/07/29/paragon-is-an-nso-competitor-and-an-american-funded-israeli-surveillance-startup-that-hacks-encrypted-apps-like-whatsapp-and-signal/</a> (accessed November 19, 2025).<br><br>

<span class="bibliography_nums">[10]</span>	C. Deiss. "„Messenger-Überwachung“: Einsatz von Spionagesoftware nach wie vor menschenrechtswidrig." Amnesty International. <a href="https://www.amnesty.at/presse/messenger-ueberwachung-einsatz-von-spionagesoftware-nach-wie-vor-menschenrechtswidrig/">https://www.amnesty.at/presse/messenger-ueberwachung-einsatz-von-spionagesoftware-nach-wie-vor-menschenrechtswidrig/</a> (accessed November 16, 2025).<br><br>

<span class="bibliography_nums">[11]</span>	C. Lab. "BLASTPASS: NSO Group iPhone Zero-Click, Zero-Day Exploit Captured in the Wild." <a href="https://citizenlab.ca/2023/09/blastpass-nso-group-iphone-zero-click-zero-day-exploit-captured-in-the-wild/">https://citizenlab.ca/2023/09/blastpass-nso-group-iphone-zero-click-zero-day-exploit-captured-in-the-wild/</a> (accessed November 17, 2025).<br><br>

<span class="bibliography_nums">[12]</span>	B. Marczak, J. Scott-Railton, B. A. Razzak, and R. Deibert. "Triple Threat: NSO Group's Pegasus Spyware Returns in 2022 with a Trio of iOS 15 and iOS 16 Zero-Click Exploit Chains." <a href="https://citizenlab.ca/2023/04/nso-groups-pegasus-spyware-returns-in-2022/">https://citizenlab.ca/2023/04/nso-groups-pegasus-spyware-returns-in-2022/</a> (accessed November 17, 2025).<br><br>

<span class="bibliography_nums">[13]</span>	T. Conference. "Cyber risks to journalists | Trust Conference 2023 | Day One." Trust Conference. <a href="https://www.youtube.com/watch?v=TTPqBw0P1zs">https://www.youtube.com/watch?v=TTPqBw0P1zs</a> (accessed November 19, 2025).<br><br>

</p>