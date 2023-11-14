---
title: Network Architecture
excerpt: In this section you'll find basic info of your Network.
weight: 2
layout: docs
---
## DMZ Deployment


<!--
$$uml
@startuml
nwdiag {
  group {
    color = "#FFaaaa";
    web01;
    db01;
  }
  group {
    color = "#aaaaFF";
    dns;
    firewall;
  }
  network dmz {
      address = "210.x.x.x/24"

      web01 [address = "210.x.x.1"];
      firewall [address = "210.x.x.2"];
  }
  network internal {
      address = "172.x.x.x/24";

      web01 [address = "172.x.x.1"];
      dns [address = "172.x.x.2"];
      db01 ;
      firewall ;
  }
}
@enduml
$$
-->
![Network](/images/network.png "Network")

## IP Allocation Scheme

| Device | Zone | Network  | IP Address |
| ------ | ---- | -------- | ---------- |
|web01   | dmz  | 210.0.0.0/24  | 210.0.0.1 | 
|firewall| dmz  | 210.0.0.0/24  | 210.0.0.2 | 
|db01    | internal | 172.0.0.0/24  | 172.0.0.1 | 
|dns     | internal | 172.0.0.0/24  | 172.0.0.2 |