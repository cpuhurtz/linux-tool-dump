# linux-tool-dump

- [disrup7](./disrup7/README.md) is a super simple LKM which leverages Net Filters and their respective function callbacks to drop some pre-defined percentage of all traffic.
    * This LKM makes no effort in hiding itself. It is non-persistent. Once remotely deployed, good luck regaining access to the box.

- [ETHERDRUNK](./ETHERDRUNK/README.md)

- [FRACTALHAMMER](./FRACTALHAMMER/README.md) is an extensive, Linux-focused keylogger. Developed by someone I'll refer to as "KVM."
    * Code needs to be revamped slightly (and tested) before being committed. Currently has three versions w/ differing features.

- [GORENEST](./GORENEST/README.md) is one part "client", one part "implant", one part "generator." Developed in less than 10 minutes by the wicked wizard [raskov](https://github.com/v1k1ngspl01ts).
    * TL;DR - receive, decrypt, execute a binary. Does not touch the target filesystem.
    * The client is responsible for encrypting and sending traffic to a pre-designated IP-PORT pair.
    * The implant listens on said port. Received traffic is interpreted as a binary destined for decrypt-and-execute.
    * The generator builds each GORENEST implant, accepting one configuration option: which port to listen on.

- [GREENPHOSPHOR](./GREENPHOSPHOR/README.md) is ...

- [REDPHOSPHOR](./REDPHOSPHOR/README.md) is ... 

- [RETROSAMURAI](./RETROSAMURAI/README.md) is an implant designed to intercept outbound application traffic and stain valid sessions with identifiable exfil data. Developed by yours truly.
    * Doing this in usermode is possible through `iptables` NFQUEUE or REDIRECT; traffic is proxy'd to `mitmproxy` or a program handling NFQueue structs.
    * Second part of RETROSAMURAI are the ALLEYWAYs: sensors placed on hosts within the same transmission/broadcast domain that would be able to detect the stain(s).
    * ALLEYWAY sensors handle bundling & exfil back to C2.
    * Enables strategic collection across disparate hosts.

- [shr0ud](./shr0ud/README.md) is a trojanized variant of `netstat`. Developed by yours truly.
    * It's intended to replace the common admin utility `/usr/bin/netstat`.
    * Features a listener that receives a crafted UDP packet to dynamically `set` or `remove` "filters."
    * Said filters are designed to remove certain `netstat` results from appearing in the output.

- [SPINALTAP](./SPINALTAP/README.md) is a work-in-progress, intended to be a trojanized variant of `sshd` which intercepts password credentials. Developed by yours truly.
    * Details to be added here at a later time.
    * Credential harvesting is finished, but still needs to be transmitted back to C2.

- [ULTRAVIOLENCE](./ULTRAVIOLENCE/README.md) is a simple implant capable of standard `cd`, `put`, `get` and `execute`. Developed in less than 20 minutes by the wicked wizard [raskov](https://github.com/v1k1ngspl01ts).
    * The client is responsible for receiving a "callback" from ULTRAVIOLENCE implant.
    * Once the session is established, client assumes command and control over the target with aforementioned four functions.
    * The generator builds each ULTRAVIOLENCE implant, accepting two configuration options: IP and PORT to callback to.

- [WHITEPHOSPHOR](./WHITEPHOSPHOR/README.md) is ...

# TODO

- Upload other tools (as long as I can still find them).
- Categorize the tools found here for easier repo navigation.
- Use tool-specific README files to elaborate on usage, OPSEC considerations, and build procedure(s).