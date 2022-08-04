---
title: System Traces
permalink: /docs/dataset/sys
redirect_from: /docs/dataset/sys.html
---
<hr style="border:.8px solid silver"> 
 
We describe more details about our device traces here.

#### Client Behavior Trace

Client device availability is dynamic in FedScale benchmarking. 
We incorporate a large-scale user [behavior dataset](https://arxiv.org/pdf/2006.06983.pdf) spanning across 136k users to emulate the behaviors of clients.
It includes 180 million trace items of client devices (e.g., battery charge or screen lock) over a week. 
We follow the real federated learning setting, which considers the device in charging to be available.

**Details**: 
`./benchmark/dataset/data/device_info/client_behave_trace` contains a list of device configurations including its active period and model type.
Here is a snapshot of the file:
```commandline
(107740, {'duration': 1, 'inactive': [88494, 93284], 'finish_time': 518400, 'active': [88494, 93283], 'model': 'SM-G611MT'}), 
(107741, {'duration': 1, 'inactive': [39055], 'finish_time': 172800, 'active': [39054], 'model': 'SM-J730GM'}), 
(107742, {'duration': 1, 'inactive': [120130], 'finish_time': 432000, 'active': [120129], 'model': 'SM-G357M'}),
(107743, {'duration': 1, 'inactive': [1], 'finish_time': 259200, 'active': [0], 'model': 'moto g(7) play'}), 
```

---
#### Client Device Capacity


We formulate the system trace of different clients using [AI Benchmark](https://arxiv.org/abs/1910.06663) and [MobiPerf Measurements](https://www.measurementlab.net/tests/mobiperf/) on mobiles. 
AI Benchmark provides the training and inference speed of diverse models (e.g., MobileNet) across
a wide range of device models (e.g., Huawei P40 and Samsung Galaxy S20), 
while MobiPerf has collected the available cloud-to-edge network throughput of over 100k world-wide mobile clients. 
As specified in [real federated learning deployments](https://arxiv.org/abs/1902.01046), we focus on mobile devices that have larger than 2GB RAM and  connect with WiFi.
 
**Details**: 
`./benchmark/dataset/data/device_info/client_device_capacity` contains a list of different devices along with their the communication and computation speed.

