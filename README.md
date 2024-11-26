# linux-tool-dump

- [FRACTALHAMMER](./FRACTALHAMMER/README.md) is an extensive, Linux-focused keylogger. Developed by someone I'll refer to as "KVM."

- [GORENEST](./GORENEST/README.md) is one part "client", one part "implant", one part "generator." Developed in less than 10 minutes by the wicked wizard `raskov`.
    * TL;DR - receive, decrypt, execute a binary. Does not touch the target filesystem.
    * The client is responsible for encrypting and sending traffic to a pre-designated IP-PORT pair.
    * The implant listens on said port. Received traffic is interpreted as a binary destined for decrypt-and-execute.
    * The generator builds each GORENEST implant, accepting one configuration option: which port to listen on.

- GREENPHOSPHOR

- RETROSAMURAI

- [shr0ud](./shr0ud/README.md) is a trojanized variant of `netstat`. Developed by yours truly.
    * It's intended to replace the common admin utility `/usr/bin/netstat`.
    * Features a listener that receives a crafted UDP packet to dynamically `set` or `remove` "filters."
    * Said filters are designed to remove certain `netstat` results from appearing in the output.

- [SPINALTAP](./SPINALTAP/README.md) is a work-in-progress, intended to be a trojanized variant of `sshd` which intercepts password credentials. Developed by yours truly.
    * Details to be added here at a later time.
    * Credential harvesting is finished, but still needs to be transmitted back to C2.

- [ULTRAVIOLENCE](./ULTRAVIOLENCE/README.md) is a simple implant capable of standard `cd`, `put`, `get` and `execute`. Developed in less than 20 minutes by the wicked wizard `raskov`.
    * The client is responsible for receiving a "callback" from ULTRAVIOLENCE implant.
    * Once the session is established, client assumes command and control over the target with aforementioned four functions.
    * The generator builds each ULTRAVIOLENCE implant, accepting two configuration options: IP and PORT to callback to.

- WHITEPHOSPHOR

# TODO

- Upload other tools (as long as I can still find them).
- Categorize the tools found here for easier navigation.
- Use tool-specific README files to elaborate on usage, OPSEC considerations, and build procedure(s).