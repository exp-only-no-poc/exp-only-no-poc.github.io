---
title: Project offer - Running your own JS code inside Windows Defender and beyond
tags: windows javascript project_offer
---

### Project Introduction 

Maybe lots of researchers are not familiar with Windows Defender but it is a default Anti-Virus engine if you install modern Windows OS with default configuration.

But it is a quite interesting **zero-click** attack surface for Windows OS. If you found any ways to drop the malicious payload within the victim machine, Windows Defender will automatically scanning the payload and **emulating** some functionalities. I think it is an interesting attack surface with some vulnerabilities like [CVE-2021-1647](https://googleprojectzero.github.io/0days-in-the-wild/0day-RCAs/2021/CVE-2021-1647.html), a vulnerability which occurred in ASProtect unpacking routine in Windows Defender and Microsoft mitigate it by eliminate the entire emulation layer of ASProtect from its product.

The [S2W](https://s2w.inc/) researchers also digging into this emulation layer and they found [CVE-2022-24548](https://medium.com/s2wblog/fuzzing-the-shield-cve-2022-24548-96f568980c0) 16-bit DOS emulation layer.

I noticed the **Google Project Zero** researchers found some vulnerabilities in JS engine emulation layer( called nScript? ) in 2017.
- https://project-zero.issues.chromium.org/issues/42450283
- https://project-zero.issues.chromium.org/issues/42450282
- https://project-zero.issues.chromium.org/issues/42450276#comment11

There are some other public materials which it worth to mention here:
- https://labs.infoguard.ch/posts/attacking_edr_part4_fuzzing_defender_scanning_and_emulation_engine/
- https://www.pixiepointsecurity.com/blog/nday-cve-2021-31985/
- https://github.com/v-p-b/loadlibrary


[Alexei Bulazel](https://x.com/0xAlexei) also diclosed some of his research about this JS emulation layer in Recon 2018.
- https://recon.cx/2018/brussels/resources/slides/RECON-BRX-2018-Reverse-Engineering-Windows-Defender-s-JavaScript-Engine.pdf

I also remember that I implemented a standalone CLI tool by hooking `JavaScriptInterpreter::eval()` to run arbitrary JS code using Windows Defender based on this slide a few years ago but I forgot about the code...I have to re-implement it but I can assure that it will be working( maybe ).

The another marketing point of this project offer is that Microsoft published the symbol for `mpengine.dll`( the core engine of windows defender ) after they updated the bug bounty rule in 2025.
- https://www.microsoft.com/en-us/msrc/bounty-defender

You can check this immediately by downloading `mpengine.dll` from [Winbindex](https://winbindex.m417z.com/) and open it with IDA.
![image 1](/images/project_offer_windows_defender_1.png)

Send DM to [@exp_only_no_poc](https://x.com/exp_only_no_poc) on X platform if you have any interest for this project!

---
