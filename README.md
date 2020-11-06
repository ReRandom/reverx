# ReverX

Communication protocols determine how network components interact with each other. Therefore, the ability to derive a specification of a protocol can be useful in various contexts, such as to support deeper black-box testing or effective defense mechanisms. Unfortunately, it is often hard to obtain the specification because systems implement closed (i.e., undocumented) protocols, or because a time consuming translation has to be performed, from the textual description of the protocol to a format readable by the tools.

To address these issues, I've developed ReverX, a Java application that generates automata for the language and protocol state machine from network traces. Since this solution only resorts to interaction samples of the protocol, it is well-suited to uncover the message formats and protocol states of closed protocols and also to automate most of the process of specifying open protocols.  It supports text-based protocols (eg, FTP, POP, etc.) and it provides a limited support for binary-based protocols (eg, DNS). It does not support encrypted payloads.

[paper](https://www.researchgate.net/profile/Joao_Antunes3/publication/221200255_Reverse_Engineering_of_Protocols_from_Network_Traces/links/0fcfd50c3eb9574ac4000000.pdf)

### BUILD
```
# ant
```

### RUN
```
### optional
# sudo cp lib/libjnetpcap.so /usr/lib/

# java -cp dist/reverx.jar:lib/jnetpcap.jar Language --pcap="test/traces-bug.pcap" --delim="\r\n" 0.5 20 t1.in
```

### CLEAN
```
# ant clean
```
