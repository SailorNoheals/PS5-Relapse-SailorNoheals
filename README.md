# PS5 Relapse Exploit
Supported firmware: 7.00 through 13.60.

## Usage
- Run `python serve.py` locally, and visit the provided URL on the PS5.
- The default payloads are stored in `payloads/` after a successful run, the ELF loader listens on port `9021`.
- After elfldr starts on port `9021`, you can press R2 to send `kstuff.elf`, `shadowmountplus.elf`, `PS5SX2Helper.elf`, then `etaHEN.elf`.
- Alternatively, You can press L2 to send only `kstuff.elf`, `PS5SX2Helper.elf`, and `shadowmountplus.elf`. This method sends `OnionHE.elf` 1 instead of `etaHEN.elf`

## Modifications by Sailor Noheals
A feature to press L2 has been added to allow the payloads to run without etaHEN being sent.

OnionHEN has been added as an alternative to etaHEN. 

The payload `PS5SX2Helper.elf` file has been added to the list of payloads sent in both the L2 and R2 methods to provide more automatic support for the PS5SX2 application on exploited PS5 systems. If PS5SX2 is crashing on launch, this may be the cause. Make sure that the helper payload is running.

## Stability notes
Webkit may need several attempts, reload the page if the browser stalls. The kernel exploit may hang or panic the console, so reboot before trying again if that happens.

## Exploit chain
Browser stage uses JSC info leaks and a structured clone object pool mismatch to corrupt a typedarray. The kernel stage combines a address leak with an `aio_multi_wait` uaf race to establish kernel r/w.

## Credits
ntfargo, ufm42, Sonic-Iso, Jordy, Dr. Yenyen, TheFlow, SlidyBat,  Flatz, cow, nhk, bollarz, Sleirsgoevy, EchoStretch, EarthOnion.

## Disclaimer
This project is intended for **educational and security research purposes only**. It does not endorse piracy, unauthorized access, or misuse of commercial devices. Use it only on devices you own or are authorized to test, and comply with applicable laws and regulations.

The software is provided as-is, without warranty. You assume the risks of using it, including system instability, data loss, and account bans. The maintainers accept no liability for resulting damage. 
