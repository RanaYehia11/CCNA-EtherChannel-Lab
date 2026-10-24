# EtherChannel Configuration Lab | Cisco Packet Tracer

## 📌 Project Overview

This project demonstrates **EtherChannel (Link Aggregation)** configuration in Cisco Packet Tracer using three methods: **LACP, PAgP, and Static EtherChannel**.

The lab connects multiple Cisco Catalyst 2960 switches using bundled physical links to practice link aggregation, negotiation modes, and verification of EtherChannel configurations.

## 🎯 Objectives

- Understand EtherChannel and link aggregation.
- Configure EtherChannel using LACP (IEEE 802.3ad).
- Configure EtherChannel using PAgP (Cisco proprietary).
- Configure Static EtherChannel without negotiation.
- Compare negotiation modes and their compatibility.
- Verify EtherChannel status using Cisco IOS commands.

## 🖥️ Lab Topology

The topology contains three EtherChannel connections between four Cisco Catalyst 2960 switches:

| Connection | Protocol | Switch A Mode | Switch B Mode |
|---|---|---|---|
| Switch4 ↔ Switch6 | LACP | Active | Passive |
| Switch5 ↔ Switch6 | PAgP | Desirable | Auto |
| Switch6 ↔ Switch7 | Static | On | On |

Each connection uses two physical Ethernet links bundled into one logical EtherChannel.

## ⚙️ Technologies & Concepts

- Cisco Packet Tracer
- Cisco Catalyst 2960 switches
- EtherChannel / Link Aggregation
- LACP (Link Aggregation Control Protocol)
- PAgP (Port Aggregation Protocol)
- Static EtherChannel
- Cisco IOS CLI
- Port-channel interfaces
- Network troubleshooting and verification

## 🔧 Configuration Summary

### 1. LACP EtherChannel

- **Active:** Actively sends LACP negotiation packets.
- **Passive:** Responds to LACP negotiation but does not initiate it.

An Active–Passive combination can successfully establish an EtherChannel.

### 2. PAgP EtherChannel

- **Desirable:** Actively initiates PAgP negotiation.
- **Auto:** Waits for PAgP negotiation from the other side.

A Desirable–Auto combination can successfully establish an EtherChannel.

### 3. Static EtherChannel

- **On / On:** Configures the EtherChannel without LACP or PAgP negotiation.

Both sides must be configured consistently. Incorrect configurations can cause connectivity issues or switching loops.

## 💻 Verification Commands

Use the following Cisco IOS commands to verify the configuration:

```text
show etherchannel summary
show etherchannel port-channel
show interfaces port-channel 1
show running-config
show interfaces trunk
```

The port-channel number may differ depending on your configuration.

### Expected Results

- The configured EtherChannel groups are displayed.
- Negotiated LACP and PAgP bundles form successfully.
- Static EtherChannel links are bundled when both ends are configured consistently.
- Member interfaces are associated with their respective port-channel interfaces.

## 🧪 Testing & Validation

After configuring the lab:

1. Verify each EtherChannel using `show etherchannel summary`.
2. Confirm that the member interfaces are bundled.
3. Check for configuration mismatches between connected switches.
4. Test connectivity where appropriate for the configured Layer 2 topology.
5. Investigate any suspended or inactive EtherChannel member ports.




## 👩‍💻 Author

**Rana Yehia Zakria**


[GitHub](https://github.com/RanaYehia11) · [LinkedIn](https://linkedin.com/in/rana-yehia-45786b289)

---

*Part of my CCNA learning journey, focused on switching, link aggregation, and practical network configuration using Cisco Packet Tracer.*
