In case of encountering strage issues, like installing packages or building an images and receiving errors like conntectionerro, could not establish a connection to pypi.org and something like that, there is a strong probability that our server does not hae intenet connection. In order to check this we should run ping command"


| IP          | Owner      | Service                     |
| ----------- | ---------- | --------------------------- |
| **1.1.1.1** | Cloudflare | Public DNS + Security + CDN |
| **8.8.8.8** | Google     | Public DNS                  |

```
ping 1.1.1.1
```

or

```
ping 8.8.8.8
```

By running ping command
You are testing:

✅ ICMP reachability

✅ Packet loss

✅ Round-trip latency (RTT)

✅ Quality of your routing path to Cloudflare vs Google

⚠️ You are NOT testing DNS resolution itself—only the network path to those servers.

If both pings fail, it means we do not have Internet on our server. But if

ping 8.8.8.8 fails

ping 1.1.1.1 works
→ This strongly suggests policy-based blocking, not a network failure.
