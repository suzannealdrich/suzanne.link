---
title: 'Stuxnet: Digital Industrial Sabotage or Cyber-Weapon of Mass Destruction?'
subtitle: ''
summary: ''
authors:
- suzanne
tags:
- technology
categories: [Essays]
date: "2011-05-06T00:00:00Z"
lastmod: "2011-05-06T00:00:00Z"
featured: true
draft: false  
---

The story of Stuxnet reads like a cross between a work of cyberpunk fiction and an international spy novel. In 2009 the world community was intensely debating the immediacy of Iran’s nuclear weapon program readiness. Meanwhile, a clandestine software project, sponsored by a cyber superpower with vast resources, was engaged in coding the first known malware rootkit to monitor and subvert the programmable logic controllers of an industrial system, allegedly the Iranian Natanz uranium enrichment facility. Since the outbreak of the worm, security researchers have studied Stuxnet intensely to determine its origin, mechanism, and target. While the suspected aim was to disrupt Iran’s nuclear program, official confirmation only came late last year, as “Iranian President Mahmoud Ahmadinejad said [in November 2010] that malicious computer code launched by “enemies” of the state had sabotaged centrifuges used in Iran’s nuclear-enrichment program.”[^1] If this were simply a story of how the ‘good guys’ prevailed over the ‘bad’, we could end the narrative here, and possibly laud the potential of cyber-warfare to avert physical combat. However, now that infecting industrial systems has evolved from a theoretical concept into an inevitable reality, it becomes the security analyst’s duty to project capabilities such as Stuxnet demonstrated onto the increasingly complex web of systems that sustain our lives.

It is not exactly clear how or when Stuxnet was first unleashed, and its purpose was also not immediately obvious. Experts suspect that in June 2009, Russian contractors working for the Iranian nuclear program inserted an infected USB stick into a system running the uranium enrichment plant.[^2] The infection was dubbed ‘Stuxnet’ by a Belarusian security firm who first detected the worm running loose in June 2010, and noticed that particular string of text in the code.[^3] Spreading through Windows computers by means of previously unknown vulnerabilities, or ‘zero-day’ exploits, the outbreak was concentrated in Iran, although systems in India, Pakistan, and Indonesia were also compromised.[^4] Usually worms are spread through the Internet directly, causing a much larger infection footprint than the mere 100,000 computers worldwide reportedly affected by Stuxnet. Relying so heavily on the mechanism of infected USB sticks and local network shares to spread itself would seem to indicate that the target was not normally connected to the Internet, and the intended system might have relied on ‘air-gap’ security, or non-connectivity to the Internet, to prevent cyber-attacks. One additional implication of this infection vector is that the spread of Stuxnet would be fairly confined to the geographical area in which it was introduced, which seems to indicate a concern for limiting potential collateral damage on the part of the mysterious authors of Stuxnet. The technically-induced limitation of the worm to a specific geographic location and the exploitation of ‘air-gap’ security typical in industrial facilities are both strong indicators that Stuxnet was specifically designed to infiltrate such a system with minimal unintended consequences.

Another clue in the mystery of the Stuxnet worm is the enormous value of the zero-day, or unpatched, vulnerabilities in Windows that were being exploited by the bug. Usually such security holes are worth a lot of money to hackers, in the neighborhood of $500,000 each on the black market. In addition, Stuxnet installed a rogue Windows driver that had been signed with stolen legitimate certificates also worth quite a considerable sum. Security expert Bruce Schneier expressed skepticism that the Stuxnet coding effort had been instigated by a typical criminal organization intent on theft or extortion, and supported the notion that it was a dedicated effort to take down a specific target:
<blockquote>Stuxnet doesn't act like a criminal worm....Stuxnet performs sabotage. It doesn't threaten sabotage, like a criminal organization intent on extortion might. Stuxnet was expensive to create. Estimates are that it took 8 to 10 people six months to write....Additionally, zero-day exploits are valuable. They're hard to find, and they can only be used once. Whoever wrote Stuxnet was willing to spend a lot of money to ensure that whatever job it was intended to do would be done.[^5]</blockquote>
Once Stuxnet infected a Windows machine, it would check for the existence of a running Siemens WinCC/PCS7 SCADA control software and take advantage of yet another zero-day vulnerability, a hard-coded password for the system’s database, to install itself. Then, if it detected that the control system was running a precise configuration of frequency-converter drives operating centrifuges at particular high speeds only found at the Natanz uranium enrichment plant, Stuxnet would insert a rogue driver into the chain of communication between the control system and the Siemens S7 PLCs which actually operate the centrifuges. This form of man-in-the-middle attack allowed Stuxnet to record sensors monitoring normal day-to-day operations, and play them back to the control software, so that nobody in charge could easily determine that anything had gone terribly wrong. But indeed, the centrifuges were being manipulated to speed up and slow down in such a manner as to hinder their ability to process uranium:
<blockquote>Using nuclear enrichment as an example, the centrifuges need to spin at a precise speed for long periods of time in order to extract the pure uranium....If those centrifuges stop to spin at that high speed, then it can disrupt the process of isolating the heavier isotopes in those centrifuges ... and the final grade of uranium you would get out would be a lower quality.[^6]</blockquote>
The sophisticated espionage and sabotage which Stuxnet performed is not a product of typical criminal syndicates, terrorists, or common hackers. It is an exercise of a superpower’s national security interest in keeping the nuclear arms field clear of competitors.

However, Stuxnet is not the first malware to have a physical effect on an industrial system, as it is suspected that the CIA caused a large trans-Siberian gas pipeline explosion in 1982, by sabotaging its SCADA control system operated by the Russians. Our country is highly interested in the new battlefields of cyber-war, and has access to the specialized facilities necessary for testing these new forms of weaponry:
<blockquote>Behind Dimona’s barbed wire, the experts say, Israel has spun nuclear centrifuges virtually identical to Iran’s at Natanz, where Iranian scientists are struggling to enrich uranium. They say Dimona tested the effectiveness of the Stuxnet computer worm, a destructive program that appears to have wiped out roughly a fifth of Iran’s nuclear centrifuges and helped delay, though not destroy, Tehran’s ability to make its first nuclear arms.[^7]</blockquote>
The most alarming implication of Stuxnet is that the concept of programming malware capable of disabling or destroying the critical systems necessary for sustaining our way of life is now in the toolkit of any sufficiently determined entity willing to invest the time and money necessary for deploying such a cyber-weapon of mass destruction. Although the nation-state responsible for Stuxnet may have taken great pains to avoid collateral damage and unintended consequences, the proverbial cat is now out of the bag.

[^1]: Kim Zetter, “Iran: Computer Malware Sabotaged Uranium Centrifuges,” Wired.com Threat Level, November 29, 2010, http://www.wired.com/threatlevel/2010/11/stuxnet-sabotage-centrifuges/.

[^2]: Mark Clayton, “Stuxnet worm mystery: What's the cyber weapon after?,” Christian Science Monitor, September 24, 2010, http://www.csmonitor.com/USA/2010/0924/Stuxnet-worm-mystery-What-s-the-cyber-weapon-after.

[^3]: “A worm in the centrifuge: An unusually sophisticated cyber-weapon is mysterious but important,” The Economist, September 30, 2010, http://www.economist.com/node/17147818.

[^4]: Nicolas Falliere, Liam O. Murchu, and Eric Chien, “W32.Stuxnet Dossier v1.4”. Symantec. February 11, 2011, http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_stuxnet_dossier.pdf.

[^5]: Bruce Schneier, “Stuxnet,” Schneier on Security, October 7, 2010, http://www.schneier.com/blog/archives/2010/10/stuxnet.html.

[^6]: Kim Zetter, “Iran: Computer Malware Sabotaged Uranium Centrifuges,” Wired.com Threat Level, November 29, 2010, http://www.wired.com/threatlevel/2010/11/stuxnet-sabotage-centrifuges/.

[^7]: William J. Broad, John Markoff and David E. Sanger, “Israeli Test on Worm Called Crucial in Iran Nuclear Delay,” The New York Times, January 15, 2011, http://www.nytimes.com/2011/01/16/world/middleeast/16stuxnet.html.