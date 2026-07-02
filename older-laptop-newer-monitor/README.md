# Older Laptop, Newer Monitor

## :seedling: Setup
**1. MSI GF63 Thin 2021 Edition (Intel I5, Nvidia Gtx 1650 Max Q)**

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/20ed60e0-af63-4b5f-98ea-44a6ed168a02" />

<br>
<br>

**2. Xiaomi 4K 60Hz Monito A27Ui**

<img width="733" height="341" alt="image" src="https://github.com/user-attachments/assets/e3fc0e3c-48d1-4c8f-9b3f-e1633ef22a8a" />

<br>
<br>

**3. Vention USB to Dual HDMI MST Adpater**

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/3c8de65f-df83-49c1-9904-3787b8a3a2bd" />

<br>
<br>

## :sweat_drops: Problem Statement
Due to the old HDMI 1.4 and data-only USB-C port, the laptop needs its GPU signal to be route through a dedicate DisplayLink adapter to drive the external monitor. 

Normally, the GPU connects directly to physical video traces on the motherboard that lead straight to a video output. But since MSI GF63 Thin's USB-C port is wired solely for USB data protocol pins, the native video signal physically can't reach the port. 
```
[NVIDIA / Intel GPU] ──(Direct Hardware Traces)──> [HDMI Port] ──> [Monitor]
[NVIDIA / Intel GPU] ──(Direct Hardware Traces)──> [USB-C Port (Data Only)] ✖ [Signal Terminated]
```

DisplayLink adapter however, ignored the physical video traces entirely. It uses the CPU to compress the display data into standard network/ USB packets, and send it across the data pins of the USB-C port. Then, the GPU chip inside the adapter will do the heavy lifting of rebuilding the video signal.

<img width="512" height="280" alt="image" src="https://github.com/user-attachments/assets/f74cdc9b-d23d-47c7-9ae9-de65c5ea3ebb" />

<br>
<br>

## :sunny: Troubleshooting Steps
