---
title: "Remote direct memory access over Ethernet"
date: 2026-08-15
categories: ROCE
tags: AI-DC
---




Notice:Before we get started , I want to share one point . It is that if we want to really know one technology knowledge, we should not just know it from the  appearance or a lot specific characteristics of written form.
We should explore the deep why human desig it we we need it.
We should be more patient and more passionate about this process instead of appearance knowledge.

Before we get started , I want to share one point . It is that if we want to really know one technology knowledge, we should not just know it from the  appearance or a lot specific characteristics of written form.
We should explore the deep why human desig it we we need it.
We should be more patient and more passionate about this process instead of appearance knowledge.

So before we explore this technology, let's take a look at what's the difference between the ai dc and traditional dc network, what's the ai dc cluster networking protocol requirement.
In the traditional data centers, like enterprise fabric or cloud data center , we just use normal architecture, like three layer architecture or two layer spine leaf already can match the data transmitted requirement.
But when we touch the AI data center, everything changes. At the AI or we can call it HPC(high performence computing) data center the data need to transmitted between difference GPU device, the  traditination socket modle for GPU too slow, because traditination network at server side higly depend on the CPU funcation to copy the data and kernel encapsulation.
To skip the CPU and kernel encapsulation, we design the Remote direct memory access technology to achieve higher transmission between different nodes.

<img width="816" height="456" alt="image" src="https://github.com/user-attachments/assets/a4cf4c35-8012-4eba-a880-daaeb236fc7c" />


RDMA technology is the most comman transmission technology bewteen GPU server, but RDMA for the tradination network (Ethernet) is a another plane technology can't direcly running at the ethernet envirorment, because tradination network modle type is Best-effort, the IP network just forwards packets on a best-effort basis. Upon errors,packet loss or out-of-order delivery the IP layer simply discards packets and performs no retransmission or error correction.
But the RDMA requires a loss-less network environment, so we design the ROCE/Infiband.
ROCE trying to design the RDMA network but basic on the ethernet(good idea because cost become more lower) but that requirment brings up another question it is tradination Ethernet IP layer just best-effort can't make sure the packet loss less, so we need configure a lot protocol to make sure the packet loss less like the priority based flow controle PFC and Explicit Congestion Notification ECN to achieve loss less this goal.
That's network side understanding about the ROCE network, but essentially not just that, about the ROCE if we want to know more we need to see how it work at server side inclduing the logical desige and physical hardware design the  data plane transmission and controle plane manager. 


[链接文字](https://leslie-2027.github.io)
