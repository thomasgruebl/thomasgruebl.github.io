---
layout: post
title:  "A Review of Internet Censorship Research"
date:   2026-06-10 18:02:00 +0100
categories: posts
excerpt: As Internet censorship continues to be deployed across a number of nation-states, understanding its scope and underlying mechanisms is more important than ever. Consequently, research on censorship measurement and circumvention has attracted growing academic interest, particularly in... <a href="https://thomasgruebl.github.io/posts/2026/06/10/a-review-of-internet-censorship-research.html">[continue reading]</a>
---



<h3> Abstract </h3>

<p>
As Internet censorship continues to be deployed across a number of nation-states, understanding its scope and underlying mechanisms is more important than ever. Consequently, research on censorship measurement and circumvention has attracted growing academic interest, particularly in recent years. This article provides an overview of the current state of the art in the field of Internet censorship measurement and circumvention research. First, a brief overview of the fundamentals is provided, followed by an in-depth analysis of 146 contemporary Internet censorship measurement and circumvention studies, predominantly those published within the last ten years, by applying a semi-systematic literature review methodology. Subsequently, the review briefly summarizes the ethical considerations in the field, it visualizes the geographical focus of censorship measurement studies, and it provides an overview of Internet protocols used to measure censorship. In addition, it presents a taxonomy of censorship circumvention tools, analyzes their key characteristics, and examines the prevalence of the underlying network protocols used in circumvention tools. The findings suggest that, while there are numerous solutions for circumventing censorship, many are niche or theoretical, and their practicality remains unknown. Although there is an observable trend toward large-scale longitudinal censorship measurement studies, the real-world effectiveness of (academic) censorship circumvention methods is rarely evaluated. Since both censorship measurement and circumvention research go hand-in-hand, there is an increasing number of measurement studies which directly translate their findings into practical circumvention strategies.
</p>

<h3>Chapter 1: Introduction</h3>

<p>
With the rapid increase in digital communication over the last decades, efforts to control and restrict the free flow of information have also been on the rise. The growing deployment of censorship techniques <span class="bibliography_nums">[1], [2], [3]</span> as well as increasing global attention to digital rights and freedoms <span class="bibliography_nums">[4], [5], [6]</span> have fundamentally shaped the field over the past decade.
</p>

<p>
Alongside censorship efforts, a variety of Internet censorship circumvention tools have emerged, which allow users to regain access to information by circumventing censorship ranging from localized and temporal restrictions to large-scale and long-term state-level interventions. Some tools are more effective and user-friendly than others, serving different levels of technical expertise. What was once the domain of tech-savvy users, human rights activists, and journalists in the early days of censorship circumvention, has now become accessible to a broader audience, in part due to the commercialization and widespread adoption of Virtual Private Network (VPN) services <span class="bibliography_nums">[7]</span>.
</p>

<p>
In addition to VPNs, encrypted overlay networks for anonymous communication, such as The Onion Routing (Tor) <span class="bibliography_nums">[8]</span>, The Invisible Internet Project (I2P) <span class="bibliography_nums">[9]</span>, or Hyphanet <span class="bibliography_nums">[10]</span>, play an important role in circumventing censorship. These networks route traffic over multiple distributed nodes and provide strong privacy and anonymity guarantees for their users.
</p>

<p>
According to the 2025 Freedom House Report <span class="bibliography_nums">[11]</span>, media freedom nowadays faces widespread challenges in over 120 countries and territories, which include arrests, violence, legal harassment, and censorship. Furthermore, the report identified a general decline in global freedom for the 19th consecutive year in 2024. This trend is also observable in the digital space, where Internet freedom is increasingly under threat. A growing number of governments have implemented different forms of Internet censorship in recent years <span class="bibliography_nums">[12]</span>. In some regions, entire segments of the population have experienced partial or complete shutdowns of Internet services, particularly during periods of political unrest or elections <span class="bibliography_nums">[13], [14], [15], [16], [17]</span>. Such government-imposed censorship is commonly implemented on an Internet Service Provider (ISP) level using firewalls, content inspection software, and the like. These tools allow authorities to block access to specific websites or online platforms. They can also filter based on network protocols, source or destination Internet Protocol (IP) addresses and ports, and Domain Name System (DNS) requests or the Transport Layer Security (TLS) Server Name Indication (SNI) field. In more extreme cases, encrypted traffic may be blocked altogether based on protocol fingerprints and statistical features of encrypted traffic; one such example was temporarily observed in China in November 2021 <span class="bibliography_nums">[18]</span>. The goal of such restrictions is often to suppress dissent, control information flow, or prevent mobilization.
</p>

<p>
Since the rise of large-scale deployments of censorship technologies, the body of research around censorship measurement and circumvention has been growing consistently. This review paper consolidates Internet censorship measurement and circumvention research. It analyzes and contextualizes different forms of measurement and circumvention techniques. Both measurement and circumvention tools utilize all commonly-used application-layer protocols, such as HTTPS, DNS, SMTP, and SSH. Examples of measurement techniques include network layer, transport layer, and application layer probing, or various fuzzing strategies that modify the values of protocol-specific fields. Whereas some measurement studies purely assess whether censors are blocking certain protocols and services (<i>e.g.</i>, <span class="bibliography_nums">[19], [20], [21], [22]</span>), others also aim to identify the physical location of the censoring devices (<i>e.g.</i>, <span class="bibliography_nums">[23], [24], [25], [26]</span>), uncover the exact blocking behavior (<i>e.g.</i>, <span class="bibliography_nums">[23], [27], [28], [29], [30]</span>), or verify if the blocking behavior remains consistent over longer periods of time (<i>e.g.</i>, <span class="bibliography_nums">[13], [14], [18], [31], [32], [33], [34]</span>). Circumvention techniques comprise proxy-based systems, publisher-centric systems, protocol behavior imitation methods, covert tunneling, refraction networking, Alibi routing, as well as pure steganographic approaches.
</p>

<p>
For example, publisher-centric circumvention leverages Content Delivery Networks (CDNs) that host content across numerous global servers, making it difficult for censors to block specific sites without disrupting essential web services. Similarly, refraction networking (formerly decoy routing) requires the help of Internet Service Providers (ISPs) to intercept and reroute user traffic intended for blocked sites through covert pathways that circumvent censorship. Unlike the two aforementioned methods which rely on support from third parties, most other circumvention approaches can be implemented by end users directly or with the assistance of volunteer networks. Additionally, in recent years, some authors <span class="bibliography_nums">[2], [35], [36]</span> have developed large-scale platforms, such as OONI <span class="bibliography_nums">[37]</span>, Censored Planet <span class="bibliography_nums">[38]</span>, and ICLab <span class="bibliography_nums">[39]</span>, that continuously perform censorship measurements around the globe and openly publish their datasets. These platforms have contributed significantly to advancing our understanding of Internet censorship practices and trends worldwide. They allow researchers to analyze censorship events in near real-time, study the evolution of blocking techniques over time, and compare censorship patterns across regions.
</p>


<h3>Chapter 2: Contributions </h3>

<p>
This study focuses explicitly on the technical aspects of Internet censorship. In particular, how it is measured, how it evolves over time, and how it can be circumvented through technical means. This paper does not aim to make claims about where conventional (non-digital) censorship is implemented, how widespread or impactful it is, or to evaluate its political, legal, or moral implications. Although there are interconnected topics, such as surveillance and content moderation, they are not the primary focus of this paper unless they contribute directly to technical developments in censorship measurement or circumvention. Similarly, while “analog” or non-technical forms of censorship, like censorship in educational publishing <span class="bibliography_nums">[40]</span> or instances of self-censorship <span class="bibliography_nums">[41]</span>, offer important insights, they fall outside the scope of this study. The specific inclusion and exclusion criteria for the literature selection process are outlined in detail in Section 4.2. In short, only peer-reviewed articles that focus on the technical aspects of Internet censorship were included. These include studies that measure censorship in real-world or simulated environments, propose new or improved circumvention tools, or apply security and privacy techniques in the context of censorship. Articles were excluded if they focused mainly on political, legal, or social issues without a strong technical component.
</p>

<p>
Fundamentally, research on Internet censorship can be grouped into offensive and defensive methods. Offensive methods are censorship techniques deployed by censors with the intent to control and restrict users from accessing certain resources. Defensive methods comprise active (i.e., censorship circumvention) and passive (i.e., non-interfering censorship measurements) techniques. This paper reviews the defensive aspects of Internet censorship. Many studies <span class="bibliography_nums">[23], [25], [42], [43], [44], [45], [46]</span> propose new circumvention strategies based on the insights gained through measurement studies. The choice of the right measurement strategies can directly lead to new evasion strategies. Since measurement and circumvention techniques go hand in hand, this review paper is the first to provide a comprehensive synthesis of the two aspects.
</p>

This paper makes the following contributions:

<ul>
    <li>A classification and synthesis of Internet censorship measurement studies, encompassing the considered network protocols, countries, study durations, and a summary of the methods and results.</li>
    <li>A classification and synthesis of Internet censorship circumvention studies, focusing on the used network protocols, the throughput, evaluation strategies, application-agnosticism, and tool-specific features.</li>
    <li>A taxonomy of Internet censorship circumvention methods, identifying and reviewing the two primary categories: routing-based and obfuscation-based techniques.</li>
    <li>An analysis of the geographic focus of censorship measurement studies from the past decade, as well as a visualization of the key technical attributes of circumvention methods, including support for bootstrapping, operational readiness, and application agnosticism.</li>
</ul>

The following Figures 1 and 2 illustrate the geographical focus of Internet censorship measurement studies and a taxonomy of Internet censorship circumvention techniques between 2015 and 2025. 

<br><br>

<div style="text-align: center;">
<b><a href="https://www.sciencedirect.com/science/article/pii/S1574013726001103/pdfft?md5=1084c5c2ad87a52b9ebb5b630fe5c37b&pid=1-s2.0-S1574013726001103-main.pdf">The remainder of the article can be found here.</a></b>
</div>

<br><br>

<div style="text-align: center;">
    <figure style="text-align: center;">
        <picture>
            <source
            srcset="/assets/2026-06-10-map-geographical-focus.svg"
            media="(prefers-color-scheme: dark)">
            <img
            src="/assets/2026-06-10-map-geographical-focus.svg"
            alt="Figure 1: Geographical Focus of Internet Censorship Measurement Studies (2015-2025).">
        </picture>
     <figcaption>
        Figure 1: Geographical Focus of Internet Censorship Measurement Studies (2015-2025). 
    </figcaption>
    </figure>
</div>

<div style="text-align: center;">
    <figure style="text-align: center;">
        <picture>
            <source
            srcset="/assets/2026-06-10-taxonomy-dark.svg"
            media="(prefers-color-scheme: dark)">
            <img
            src="/assets/2026-06-10-taxonomy-light.svg"
            alt="Figure 2: Taxonomy of Internet censorship circumvention techniques (2015–2025).">
        </picture>
     <figcaption>
        Figure 2: Taxonomy of Internet censorship circumvention techniques (2015–2025). 
    </figcaption>
    </figure>
</div>




<h3> References </h3>

<p>

<span class="bibliography_nums">[1]</span>	R.S. Raman, A. Stoll, J. Dalek. "Measuring the Deployment of Network Censorship Filters at Global Scale." In: <i>Network and Distributed Systems Security (NDSS) Symposium 2020</i>, 2020.<br><br>

<span class="bibliography_nums">[2]</span>	R.S. Raman, P. Shenoy, K. Kohls, R. Ensafi. "Censored Planet: An Internet-wide, Longitudinal Censorship Observatory." In: <i>Proceedings of the 2020 ACM SIGSAC Conference on Computer and Communications Security</i>, 2020, pp. 49–66.<br><br>

<span class="bibliography_nums">[3]</span>	N.P. Hoang, S. Doreen, M. Polychronakis. "Measuring I2P Censorship at a Global Scale." In: <i>9th USENIX Workshop on Free and Open Communications on the Internet (FOCI 19)</i>, 2019.<br><br>

<span class="bibliography_nums">[4]</span>	The Citizen Lab. "The Citizen Lab." <a href="https://citizenlab.ca/">https://citizenlab.ca/</a> (accessed 2025).<br><br>

<span class="bibliography_nums">[5]</span>	Amnesty International. "Freedom of Expression." <a href="https://www.amnesty.org/en/what-we-do/freedom-of-expression/">https://www.amnesty.org/en/what-we-do/freedom-of-expression/</a> (accessed 2025).<br><br>

<span class="bibliography_nums">[6]</span>	L. Taylor. "What is Data Justice? The Case for Connecting Digital Rights and Freedoms Globally." <i>Big Data & Society</i> 4 (2) (2017): 2053951717736335.<br><br>

<span class="bibliography_nums">[7]</span>	R. Ramesh, A. Vyas, R. Ensafi. "All of Them Claim to Be the Best: Multi-perspective Study of VPN Users and VPN Providers." In: <i>32nd USENIX Security Symposium (USENIX Security 23)</i>, 2023, pp. 5773–5789.<br><br>

<span class="bibliography_nums">[8]</span>	T. T. P. Inc. "The Tor Project." <a href="https://www.torproject.org/">https://www.torproject.org/</a> (accessed 2025).<br><br>

<span class="bibliography_nums">[9]</span>	T. I. I. Project. "The Invisible Internet Project." <a href="https://geti2p.net/en/">https://geti2p.net/en/</a> (accessed 2025).<br><br>

<span class="bibliography_nums">[10]</span>	F. Project. "Hyphanet." <a href="https://www.hyphanet.org/">https://www.hyphanet.org/</a> (accessed 2025).<br><br>

<span class="bibliography_nums">[11]</span>	F. House. <i>Freedom in the World 2025: The Uphill Battle to Safeguard Rights</i>. <a href="https://freedomhouse.org/sites/default/files/2025-03/FITW_World2025digitalN.pdf">https://freedomhouse.org/sites/default/files/2025-03/FITW_World2025digitalN.pdf</a> (accessed 2025).<br><br>

<span class="bibliography_nums">[12]</span>	M.S. Al-Zaman, M.M.S. Noman. "Rise of Digital Authoritarianism? Exploring Global Motivations Behind Governmental Social Media Censorship." <i>Journal of the European Institute for Communication and Culture</i> 31 (4) (2024): 529–544.<br><br>

<span class="bibliography_nums">[13]</span>	R. Ramesh, R.S. Raman, A. Virkud, A. Dirksen, A. Huremagic, D. Fifield, D. Rodenburg, R. Hynes, D. Madory, R. Ensafi. "Network Responses to Russia’s Invasion of Ukraine in 2022: A Cautionary Tale for Internet Freedom." In: <i>32nd USENIX Security Symposium (USENIX Security 23)</i>, 2023, pp. 2581–2598.<br><br>

<span class="bibliography_nums">[14]</span>	V. Ververis, T. Ermakova, M. Isaakidis, S. Basso, B. Fabian, S. Milan. "Understanding Internet Censorship in Europe: The Case of Spain." In: <i>Proceedings of the 13th ACM Web Science Conference 2021</i>, 2021, pp. 319–328.<br><br>

<span class="bibliography_nums">[15]</span>	R. Padmanabhan, A. Filastò, M. Xynou, R.S. Raman, K. Middleton, M. Zhang, D. Madory, M. Roberts, A. Dainotti. "A Multi-perspective View of Internet Censorship in Myanmar." In: <i>Proceedings of the ACM SIGCOMM 2021 Workshop on Free and Open Communications on the Internet</i>, 2021, pp. 27–36.<br><br>

<span class="bibliography_nums">[16]</span>	R.S. Raman, L. Evdokimov, E. Wurstrow, J.A. Halderman, R. Ensafi. "Investigating Large Scale HTTPS Interception in Kazakhstan." In: <i>Proceedings of the ACM Internet Measurement Conference</i>, 2020, pp. 125–132.<br><br>

<span class="bibliography_nums">[17]</span>	T. Freyburg, L. Garbe. "Blocking the Bottleneck: Internet Shutdowns and Ownership at Election Times in Sub-Saharan Africa." <i>International Journal of Communication</i> 12 (2018): 3896–3916.<br><br>

<span class="bibliography_nums">[18]</span>	M. Wu, J. Sippe, D. Sivakumar, J. Burg, P. Anderson, X. Wang, K. Bock, A. Houmansadr, D. Levin, E. Wustrow. "How the Great Firewall of China Detects and Blocks Fully Encrypted Traffic." In: <i>32nd USENIX Security Symposium (USENIX Security 23)</i>, 2023, pp. 2653–2670.<br><br>

<span class="bibliography_nums">[19]</span>	K. Singh, G. Grover, V. Bansal. "How India Censors the Web." In: <i>Proceedings of the 12th ACM Conference on Web Science</i>, 2020, pp. 21–28.<br><br>

<span class="bibliography_nums">[20]</span>	A. McDonald, M. Bernhard, L. Valenta, B. VanderSloot, W. Scott, N. Sullivan, J.A. Halderman, R. Ensafi. "403 Forbidden: A Global View of CDN Geoblocking." In: <i>Proceedings of the 18th ACM Internet Measurement Conference</i>, 2018, pp. 218–230.<br><br>

<span class="bibliography_nums">[21]</span>	O. Farnan, A. Darer, J. Wright. "Poisoning the Well: Exploring the Great Firewall’s Poisoned DNS Responses." In: <i>Proceedings of the 2016 ACM on Workshop on Privacy in the Electronic Society</i>, 2016, pp. 95–98.<br><br>

<span class="bibliography_nums">[22]</span>	V. Ververis, G. Kargiotakis, A. Filastò, B. Fabian, A. Alexandros. "Understanding Internet Censorship Policy: The Case of Greece." In: <i>5th USENIX Workshop on Free and Open Communications on the Internet (FOCI 15)</i>, 2015.<br><br>

<span class="bibliography_nums">[23]</span>	R.S. Raman, M. Wang, J. Dalek, J. Mayer, R. Ensafi. "Network Measurement Methods for Locating and Examining Censorship Devices." In: <i>Proceedings of the 18th International Conference on Emerging Networking EXperiments and Technologies</i>, 2022, pp. 18–34.<br><br>

<span class="bibliography_nums">[24]</span>	D. Xue, R. Ramesh, L. Evdokimov, A. Viktorov, A. Jain, E. Wustrow, S. Basso, R. Ensafi. "Throttling Twitter: An Emerging Censorship Technique in Russia." In: <i>Proceedings of the 21st ACM Internet Measurement Conference</i>, 2021, pp. 435–443.<br><br>

<span class="bibliography_nums">[25]</span>	T.K. Yadav, A. Sinha, D. Gosain, P.K. Sharma, S. Chakravarty. "Where The Light Gets In: Analyzing Web Censorship Mechanisms in India." In: <i>Proceedings of the Internet Measurement Conference 2018</i>, 2018, pp. 252–264.<br><br>

<span class="bibliography_nums">[26]</span>	F. Li, A. Razaghpanah, A.M. Kakhki, A.A. Niaki, D. Choffnes, P. Gill, A. Mislove. "liberate: A Library for Exposing (Traffic-Classification) Rules and Avoiding Them Efficiently." In: <i>Proceedings of the 2017 Internet Measurement Conference</i>, 2017, pp. 128–141.<br><br>

<span class="bibliography_nums">[27]</span>	D. Katira, G. Grover, K. Singh, V. Bansal. "CensorWatch: On the Implementation of Online Censorship in India." <i>Free and Open Communications on the Internet (FOCI)</i>, 2023.<br><br>

<span class="bibliography_nums">[28]</span>	A. Bhaskar, P. Pearce. "Many Roads Lead To Rome: How Packet Headers Influence DNS Censorship Measurement." In: <i>31st USENIX Security Symposium (USENIX Security 22)</i>, 2022, pp. 449–464.<br><br>

<span class="bibliography_nums">[29]</span>	J. Jermyn, N. Weaver. "Autosonda: Discovering Rules and Triggers of Censorship Devices." In: <i>7th USENIX Workshop on Free and Open Communications on the Internet (FOCI 17)</i>, 2017.<br><br>

<span class="bibliography_nums">[30]</span>	G. Aceto, A. Botta, A. Pescapé, M.F. Awan, T. Ahmad, S. Qaisar. "Analyzing Internet Censorship in Pakistan." In: <i>2016 IEEE 2nd International Forum on Research and Technologies for Society and Industry Leveraging a Better Tomorrow (RTSI)</i>, IEEE, 2016, pp. 1–6.<br><br>

<span class="bibliography_nums">[31]</span>	N.P. Hoang, J. Dalek, M. Crete-Nishihata, N. Christin, V. Yegneswaran, M. Polychronakis, N. Feamster. "GFWeb: Measuring the Great Firewall’s Web Censorship at Scale." In: <i>33rd USENIX Security Symposium (USENIX Security 24)</i>, 2024.<br><br>

<span class="bibliography_nums">[32]</span>	E. Tsai, R.S. Raman, A. Prakash, R. Ensafi. "Modeling and Detecting Internet Censorship Events." In: <i>Network and Distributed System Security (NDSS) Symposium</i>, 2024.<br><br>

<span class="bibliography_nums">[33]</span>	Z.S. Bischof, K. Pitcher, E. Carisimo, A. Meng, R.B. Nunes, R. Padmanabhan, M.E. Roberts, A.C. Snoeren, A. Dainotti. "Destination Unreachable: Characterizing Internet Outages and Shutdowns." In: <i>Proceedings of the ACM SIGCOMM 2023 Conference</i>, 2023, pp. 608–621.<br><br>

<span class="bibliography_nums">[34]</span>	P. Gill, M. Crete-Nishihata, J. Dalek, S. Goldberg, A. Senft, G. Wiseman. "Characterizing Web Censorship Worldwide: Another Look at the OpenNet Initiative Data." <i>ACM Transactions on the Web (TWEB)</i> 9 (1) (2015): 1–29.<br><br>

<span class="bibliography_nums">[35]</span>	A. Filasto, J. Appelbaum. "OONI: Open Observatory of Network Interference." In: <i>2nd USENIX Workshop on Free and Open Communications on the Internet (FOCI 12)</i>, 2012.<br><br>

<span class="bibliography_nums">[36]</span>	A.A. Niaki, S. Cho, Z. Weinberg, N.P. Hoang, A. Razaghpanah, N. Christin, P. Gill. "ICLab: A Global, Longitudinal Internet Censorship Measurement Platform." In: <i>2020 IEEE Symposium on Security and Privacy (SP)</i>, IEEE, 2020, pp. 135–151.<br><br>

<span class="bibliography_nums">[37]</span>	A. Filasto, J. Appelbaum. "OONI: Open Observatory of Network Interference." <a href="https://ooni.org/">https://ooni.org/</a> (accessed 2012).<br><br>

<span class="bibliography_nums">[38]</span>	R.S. Raman, P. Shenoy, K. Kohls, R. Ensafi. "Censored Planet." <a href="https://censoredplanet.org/">https://censoredplanet.org/</a> (accessed 2020).<br><br>

<span class="bibliography_nums">[39]</span>	A.A. Niaki, S. Cho, Z. Weinberg, N.P. Hoang, A. Razaghpanah, N. Christin, P. Gill. "ICLab: A Global, Longitudinal Internet Censorship Measurement Platform." <a href="https://iclab.org/">https://iclab.org/</a> (accessed 2020).<br><br>

<span class="bibliography_nums">[40]</span>	C.L. Givens. "Hidden Forms of Censorship and Their Impact." <i>Bookbird</i> 47 (3) (2009): 22.<br><br>

<span class="bibliography_nums">[41]</span>	P. Cook, C. Heilmann. "Censorship and Two Types of Self-Censorship." 6 (2) (2010).<br><br>

<span class="bibliography_nums">[42]</span>	S. Nourin, V. Tran, X. Jiang, K. Bock, N. Feamster, N.P. Hoang, D. Levin. "Measuring and Evading Turkmenistan’s Internet Censorship: A Case Study in Large-Scale Measurements of a Low-Penetration Country." In: <i>Proceedings of the ACM Web Conference 2023</i>, 2023, pp. 1969–1979.<br><br>

<span class="bibliography_nums">[43]</span>	A. Amich, B. Eshete, V. Yegneswaran, N.P. Hoang. "DeResistor: Toward Detection-Resistant Probing for Evasion of Internet Censorship." In: <i>32nd USENIX Security Symposium (USENIX Security 23)</i>, 2023, pp. 2617–2633.<br><br>

<span class="bibliography_nums">[44]</span>	K. Bock, G. Naval, K. Reese, D. Levin. "Even Censors Have a Backup: Examining China’s Double HTTPS Censorship Middleboxes." In: <i>Proceedings of the ACM SIGCOMM 2021 Workshop on Free and Open Communications on the Internet</i>, 2021, pp. 1–7.<br><br>

<span class="bibliography_nums">[45]</span>	K. Bock, G. Hughey, X. Qiang, D. Levin. "Geneva: Evolving Censorship Evasion Strategies." In: <i>Proceedings of the 2019 ACM SIGSAC Conference on Computer and Communications Security</i>, 2019, pp. 2199–2214.<br><br>

<span class="bibliography_nums">[46]</span>	Z. Wang, Y. Cao, Z. Qian, C. Song, S.V. Krishnamurthy. "Your State Is Not Mine: A Closer Look at Evading Stateful Internet Censorship." In: <i>Proceedings of the 2017 Internet Measurement Conference</i>, 2017, pp. 114–127.<br><br>



</p>
