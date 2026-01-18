---
layout: post
title:  "A Personal Data Security Strategy"
date:   2026-01-18 22:17:00 +0100
categories: posts
excerpt: Amidst growing technofeudalism, platform access and its convenience have become the new land that you pay rent for using your personal data and (infra)structural dependence, sometimes because of a lack of alternatives. To prevent certain platforms from (ab)using your (meta)data... <a href="https://thomasgruebl.github.io/posts/2026/01/18/a-personal-data-security-strategy.html">[continue reading]</a>
---


<h3>Chapter 1: Introduction</h3>

<p>
Amidst growing technofeudalism, platform access and its convenience have become the new land that you pay rent for using your personal data and (infra)structural dependence, sometimes because of a lack of alternatives. To prevent certain platforms from (ab)using your (meta)data, you need to take back control of your personal data. In this article, we discuss a reasonably secure data security strategy — an offline alternative, which does not rely on any cloud storage and is resistant to various threats including online data breaches, clandestine data mining, profiling, home intrusions, etc. Convenience often comes at the expense of decreased personal autonomy, so, of course, the proposed strategy is not the most convenient, but it is one that provides security and full control over your personal data.
</p>


<h3>Chapter 2: Data Security Strategy</h3>

<p>
This chapter outlines an offline data security strategy in the form of a flow diagram. The following items are required:<br>

<ul>
    <li>3 YubiKeys (or equivalent)</li>
    <li>3 external SSDs</li>
    <li>A Linux machine</li>
</ul> 
</p>

<p>
Figure 1 depicts the legend for the following flow diagram. Figure 2 depicts the data security strategy flow diagram.
</p>


<div style="text-align: center;">
    <figure style="text-align: center;">
        <picture>
            <source
            srcset="/assets/2026-01-18-legend-dark.svg"
            media="(prefers-color-scheme: dark)">
            <img
            src="/assets/2026-01-18-legend-light.svg"
            alt="Data Security Strategy Legend">
        </picture>
     <figcaption>
        Figure 1: Data Security Strategy Legend.
    </figcaption>
    </figure>
</div>

<br>
<p>
Operational roots of trust. First, operational roots of trust are devices or services that, when compromised, would enable an attacker to gain control of your accounts. In this context, YubiKeys [1] and your Proton Account [2] are considered roots of trust because they are used to access and recover most of your other accounts. Similarly, a crypto hardware ledger represents a root of trust, as it protects private keys required to authorize transactions. KeePass XC [3] DB#1 is not considered a root of trust, because access to the database alone does not allow an attacker to authenticate to your accounts without also compromising your additional authentication factors.
</p>

<p>
To start, you should obtain three YubiKeys or equivalent hardware authentication devices: one for everyday-use, one securely stored at home as a local backup as well as for portable use, and a third one securely stored at an off-site backup location. YubiKeys allow you to store hardware-bound passkeys using the FIDO2 standard, generate One-Time Passwords (OTP) using the Initiative for Open Authentication (OATH) standard, and store cryptographic keys as per the Personal Identity Verification (PIV) standard [4]. Wherever possible, configure your online accounts to use OATH or FIDO2-based 2FA.
</p>

<p>
Next, three external hard drives are required — again, one for local (regular) backups, one securely stored at home as a local backup as well as for portable use, and a third one securely stored at an off-site backup location. Before the first use, make sure to encrypt the hard drives using VeraCrypt.
</p><br>

<div style="text-align: center;">
    <figure style="text-align: center;">
        <picture>
            <source
            srcset="/assets/2026-01-18-main-dark.svg"
            media="(prefers-color-scheme: dark)">
            <img
            src="/assets/2026-01-18-main-light.svg"
            alt="Data Security Strategy Flow Diagram">
        </picture>
    <figcaption>
        Figure 2: Data Security Strategy Flow Diagram.
    </figcaption>
    </figure>
</div>


<br>
<p>
In general, this data security strategy follows the simple principle to only backup sensitive passwords digitally, if they are non-master passwords, meaning passwords which alone do not allow anyone to access a service. Master passwords, on the other hand, are passwords that if leaked, will provide direct access to a critical service. For instance, a YubiKey PIN alone is not considered a master password since it is only useful in conjunction with the physical YubiKey. A cloud storage  password without a second authentication factor, however, is enough to gain access to all your data — hence it's a master password. If only a single password is required to gain access, such as the recovery words of a crypto hardware ledger, then don't back them up digitally, or at least don't back all recovery words up in one place.
</p>

<p>
In the flow diagram, the normal and the hidden VeraCrypt volumes appear as two separate volumes, although in practice a hidden volume resides within the free space of the normal (outer) volume. You can create a normal volume in addition to another normal+hidden volume, where you fill the outer normal volume with some rubbish data.
</p>

<p>
As for the password databases themselves, you should clearly separate sensitive passwords from less-sensitive ones. Hence, create one KeePass XC database for daily use, which is stored simply on your laptop and also within your normal VeraCrypt volume as a "local backup", just in case the KeePass Database XML (KDBX) file gets corrupted. As for the more sensitive passwords and keys, create a separate KDBX file which is exclusively stored within a hidden VeraCrypt volume and does not reside anywhere else on your disk. This file could contain sensitive passkeys or passwords that are too complex to remember. It could also contain the YubiKey FIDO2 PIN and OATH password. The fact that this KDBX file is stored inside a hidden VeraCrypt volume means it is <i>(i)</i> difficult to prove its existence and <i>(ii)</i> encrypted twice in case there is a vulnerability in either KeePass XC's or VeraCrypt's encryption schemes, thus providing you with an additional layer of security. Of course, you should only mount the volume and decrypt the database in a trusted environment.
</p>

<p>
Backup the VeraCrypt volume file as well as your KDBX file for normal passwords to your external SSD. The external SSD itself should be protected with full disk encryption. 
One of your physical backups, comprising one external SSD and one YubiKey, should be stored off-site, in a different location, such as your grandma's basement (unless you live in your grandma's basement).
<p>

<p>
You can also consider adding two-factor authentication to your Linux Unified Key Setup (LUKS)-encrypted drive using the YubiKey with a challenge-and-response scheme.
</p>

<p>
Lastly, the passwords that should never be backed up (at least not digitally) are your LUKS and  KeePass XC DB#2 decryption passwords, your VeraCrypt decryption password for your external SSDs as well as the VeraCrypt volume decryption passwords and your phone PIN.
</p>







<h3>Chapter 3: Conclusion</h3>

<div style="text-align: center;">
    <figure style="text-align: center;">
        <picture>
            <source
            srcset="/assets/2026-01-18-xkcd-comic-dark-tmp.png"
            media="(prefers-color-scheme: dark)">
            <img
            src="/assets/2026-01-18-xkcd-comic-light.png"
            alt="XKCD Comic">
        </picture>
    <figcaption>
        Figure 3: xkcd Comic [5].
    </figcaption>
    </figure>
</div>



<h3> References </h3>
<p>

<span class="bibliography_nums">[1]</span>	Yubico AB (publ). "YubiKey 5C NFC." <a href="https://www.yubico.com/ch/product/yubikey-5c-nfc/">https://www.yubico.com/ch/product/yubikey-5c-nfc/</a> (accessed January 17, 2026).<br><br>

<span class="bibliography_nums">[2]</span>	Proton AG. "A better internet starts with privacy and freedom." <a href="https://proton.me/">https://proton.me/</a> (accessed January 17, 2026).<br><br>

<span class="bibliography_nums">[3]</span> KeePassXC Team. "KeePassXC: Cross-platform Password Manager." <a href="https://keepassxc.org/">https://keepassxc.org/</a> (accessed January 17, 2026).<br><br>

<span class="bibliography_nums">[4]</span> Yubico AB (publ). "OATH overview." <a href="https://docs.yubico.com/yesdk/users-manual/application-oath/oath-overview.html">https://docs.yubico.com/yesdk/users-manual/application-oath/oath-overview.html</a> (accessed January 15, 2026).<br><br>

<span class="bibliography_nums">[5]</span> Randall Munroe. "xkcd Security." <a href="https://xkcd.com/538/">https://xkcd.com/538/</a> (accessed January 17, 2026).<br><br>


</p>
