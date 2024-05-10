# Network Traffic Simulation using Scapy and TensorFlow

This Python script demonstrates how to simulate network traffic using the Scapy library and create TensorFlow datasets and data loaders for further AI processing. It generates synthetic network traffic data for different wireless protocols, including 802.11 (Wi-Fi), 3G GSM, 4G LTE, and 5G NR.

## Motivating Articles and Related Work

Yocam, E., Gawanmeh, A., Alomari, A. et al. 5G mobile networks: reviewing security control correctness for mischievous activity. SN Appl. Sci. 4, 304 (2022). https://doi.org/10.1007/s42452-022-05193-8
https://link.springer.com/article/10.1007/s42452-022-05193-8

E. Yocam, "Narrow-band Internet of Things Protocol Standards: Survey of Security and Privacy Control Effectiveness," 2020 International Symposium on Networks, Computers and Communications (ISNCC), Montreal, QC, Canada, 2020, pp. 1-6, doi: 10.1109/ISNCC49221.2020.9297222. https://ieeexplore.ieee.org/abstract/document/9297222

Kayisu, A.K.; Kambale, W.V.; Benarbia, T.; Bokoro, P.N.; Kyamakya, K. A Comprehensive Literature Review on Artificial Dataset Generation for Repositioning Challenges in Shared Electric Automated and Connected Mobility. Symmetry 2024, 16, 128. https://doi.org/10.3390/sym16010128. 
https://www.mdpi.com/2073-8994/16/1/128

Malware Traffic Analysis (pcap and malware) https://www.malware-traffic-analysis.net/

## Features

- Generates synthetic network traffic data for various wireless protocols
- Simulates traffic flow through a proxy and reverse proxy
- Creates TensorFlow datasets and data loaders for each traffic type
- Prints a summary of the generated traffic and simulation results

## Synthetic Data Construction

The script generates synthetic network traffic data by creating packets with random payload messages that simulate a mobile user browsing an e-commerce website. The payload messages include HTTP requests for viewing products, adding items to the cart, and proceeding to checkout.

The synthetic data is constructed using the Scapy library, which allows for the creation and manipulation of network packets. The script defines functions to generate packets for each wireless protocol, incorporating the necessary headers and fields specific to each protocol.

## GTP (GPRS Tunneling Protocol)

GTP is a protocol used in mobile networks, specifically in GPRS, 3G (UMTS), 4G (LTE), and 5G networks. It is responsible for tunneling user data and signaling messages between different network nodes.

The script includes a custom `GTPHeader` class that represents a simplified version of the GTP header. The GTP header contains fields such as version, protocol type, message type, length, and TEID (Tunnel Endpoint Identifier).

## Wireless Protocol Formats

The script generates synthetic network traffic for the following wireless protocols:

### 802.11 (Wi-Fi)

- Uses the `RadioTap`, `Dot11`, `LLC`, and `SNAP` layers from Scapy
- Generates random source and destination MAC addresses
- Includes the IP, TCP, and payload layers

### 3G GSM

- Uses the `IP`, `UDP`, and `GTPHeader` layers from Scapy
- Includes the inner IP, UDP, and payload layers
- Generates a random TEID for the GTP header

### 4G LTE

- Similar to 3G GSM, but uses the `GTPHeader` layer specific to LTE

### 5G NR

- Similar to 4G LTE, but represents the 5G New Radio protocol

## Usefulness

This script is useful for:

- Generating synthetic network traffic data for testing and evaluation purposes
- Simulating traffic flow through proxies and reverse proxies
- Creating TensorFlow datasets and data loaders for further AI processing and analysis
- Understanding the structure and flow of network traffic for different wireless protocols

By generating synthetic data, the script provides a controlled environment for testing and developing network analysis tools and AI models. The created TensorFlow datasets and data loaders can be used as input for training and evaluating AI algorithms in network security, anomaly detection, and performance optimization tasks.

**Disclaimer**
This repository is intended for educational and research purposes.

