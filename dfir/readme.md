### edu
* [start.mr URL summary from SANS DFIR summit 2021](https://start.me/p/xbgNmz/sans-dfir-2021)
* [IR capability matrix](https://github.com/swannman/ircapabilities)

### tools
* [Eric Zimmerman's tools](https://ericzimmerman.github.io/#!index.md)
* [Sample files for the Deployment Research Blog](https://github.com/DeploymentResearch/DRFiles/tree/master/Scripts)
* [moneta - live usermode memory analysis tool for Windows with the capability to detect malware IOCs](https://github.com/forrest-orr/moneta)
* [ThreatHunting-Keywords - big csv file for blue/red](https://github.com/mthcht/ThreatHunting-Keywords)
* [Rapidly Search and Hunt through Windows Forensic Artefacts](https://github.com/WithSecureLabs/chainsaw)
* [Sentinel_KQL](https://github.com/ep3p/Sentinel_KQL)

### misc

* [Hunting for advanced Tactics, Techniques and Procedures (TTPs)](https://cyberpolygon.com/materials/hunting-for-advanced-tactics-techniques-and-procedures-ttps/)
* [Automate malware analysis JPCERT](https://blogs.jpcert.or.jp/en/2023/01/cloud_malware_analysis.html)
* [Carbon Black hunting](https://github.com/0xpwntester/CB-Threat-Hunting)
* [Detect Impacket wmiexec](https://twitter.com/JohnLaTwC/status/1410671329104199681)
  * [wmiexec.py](https://github.com/SecureAuthCorp/impacket/blob/master/examples/wmiexec.py) 
* [DFIR_Resources_REvil_Kaseya](https://github.com/cado-security/DFIR_Resources_REvil_Kaseya) 
* [Sysmon Internals](https://undev.ninja/sysmon-internals-from-file-delete-event-to-kernel-code-execution/)
* [Reverse Engineering an Obfuscated Malicious Macro](https://medium.com/walmartglobaltech/reverse-engineering-an-obfuscated-malicious-macro-3fd4d4f9c439)
* [Windows Process Internals: A few Concepts to know before jumping on Memory Forensics [Part 2] – ldrmodules](https://eforensicsmag.com/windows-process-internals-a-few-concepts-to-know-before-jumping-on-memory-forensics-part-2-ldrmodules-by-kirtar-oza/)
* [Detecting Post-Compromise Threat Activity in Microsoft Cloud Environments](https://www.cisa.gov/uscert/ncas/alerts/aa21-008a)
* [Visualize Windows Event logs](https://github.com/JPCERTCC/LogonTracer)
* [dump evtx in rust](https://github.com/omerbenamram/evtx)
* [dfir arfifacts](https://github.com/ForensicArtifacts/artifacts)

![image](https://user-images.githubusercontent.com/9626439/124276971-c7b94900-db44-11eb-9a86-62dd6d1a1755.png)

* [#HuntingTipOfTheDay If your DNS logging suddenly shows a machine resolving http://raw.githubusercontent.com that never normally does it, there might be a reason:](https://twitter.com/JohnLaTwC/status/1410441322310168576)

![image](https://user-images.githubusercontent.com/9626439/124277349-3bf3ec80-db45-11eb-91c7-1a83a9640cc9.png)

* [Search command lines for wildcarded file types and you might find ransomware or preparation for exfil. It will often find backup programs too so look for outlier commands.](https://twitter.com/JohnLaTwC/status/1409902619825348613)

![image](https://user-images.githubusercontent.com/9626439/124277626-883f2c80-db45-11eb-9097-ff5998af901c.png)

* [#HuntingTipOfTheDay 
Search for sc.exe changing rights on services with sdset and an ACE like: (A;;CCDCLCSWRPLORCWDWO;;;x) where x in ('AU','IU','BU','WD') You might find an elevation of privilege vuln or a sneaky attacker](https://twitter.com/JohnLaTwC/status/1409559424201498632)

![image](https://user-images.githubusercontent.com/9626439/124277869-d5bb9980-db45-11eb-8d7a-97b61ebe2d3b.png)

