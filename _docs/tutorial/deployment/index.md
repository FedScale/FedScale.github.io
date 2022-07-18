---
title: Deployment
permalink: /docs/tutorial/deployment
redirect_from: /docs/tutorial/deployment
---
<hr style="border:.8px solid silver"> 
 
This tutorial will show you how to set up and start an FL experiment to train ShuffleNet on the FEMNIST dataset using FedScale.
 
### Preliminary

Check the [instructions]({{ "/docs/home/"  | relative_url }}) to set up your environment and follow the instructions below to download the FEMNIST dataset. Here femnist is the `dataset_name`:

```
# Run `fedscale dataset help` for more details
`fedscale dataset download [dataset_name]`   # Or `bash download.sh download [dataset_name] `
```


Please make sure you are using the correct environment.
```bash
conda activate fedscale
```


***Create experiment profile***: 
Go to `benchmark/configs/femnist/` directory and modify/create your **[configuration file](https://github.com/SymbioticLab/FedScale/blob/master/benchmark/configs/femnist/conf.yml)** to submit your job. 
Modify the configurations such as the number of participants per round, the aggregation algorithm, the client optimizer, the training model, etc. based on your need.
 
<!-- #### Submit Your FL Job

Use `fedscale driver submit [conf_yml_path]` (Or `python docker/driver.py submit`) to submit your FL job. It will automatically launch the `aggregator.py` and `executor.py` to start the FL evaluation.
You can either choose to evaluate your large-scale FL experiment over a GPU cluster or test your code on your local machine.

To stop your job:
```
fedscale driver stop [job_name]
# Or python docker/driver.py stop [job_name] (specified in the yml config) -->
<!-- ``` -->

<hr style="border:.8px solid silver">

### Evaluate on a Local Machine
Follow the following instruction to run FedScale locally (i.e., standalone mode).

- ***Submitting to driver***:
It is more convenient to first test your code without a GPU cluster. 
First add an argument `- use_cuda:  False` under job_conf in your configuration file `benchmark/configs/femnist/conf.yml` if you are training without using any GPU. 
Set `ps_ip` and `worker_ips` to be `localhost` and `localhost:[x]` by default, where x represent how many executors you want to run on your local machine.
Then run the following command to start your FL job:
```
fedscale drive start benchmark/configs/femnist/conf.yml
# or python driver.py start benchmark/configs/femnist/conf.yml
```

- ***Running with Jupyter***:
We also provide jupyter notebook [examples](https://github.com/SymbioticLab/FedScale/tree/master/examples/notebook) to run your code locally.
You can first start running [server](https://github.com/SymbioticLab/FedScale/tree/master/examples/notebook/fedscale_demo_server.ipynb), 
and then run the [client](https://github.com/SymbioticLab/FedScale/tree/master/examples/notebook/fedscale_demo_client.ipynb).

<hr style="border:.8px solid silver">
### Evaluate on a Cluster
Follow the following instruction to run FedScale in a cluster (i.e., distributed mode or cross-silo FL deployment).

- ***Set up cluster***: Please assure that these paths are consistent across all nodes so that FedScale simulator can find the right path.

	+ Coordinator node: Make sure that the coodinator (master node) has access to other worker nodes via ```ssh```. 

	+ All nodes: Follow [this](../home/index.md) to install all necessary libs, and then download the datasets.

- ***Set up job configuration***:
Change `ps_ip` and `worker_ips` to the host name of your nodes in the configuration file.
For example, using 10.0.0.2:[4,4] as one of the worker_ips means launching four executors on each of the first two GPUs on 10.0.0.2 to train your model in a space/time sharing fashion. 
**Make sure the node you submit the job has access to other nodes, and you have synchronized the code across all the nodes.**

- ***Submit/Stop FL job***:
We provide an example of submitting/stopping a training job, whereby the user can submit jobs on the master node. 

	+ `fedscale driver submit [conf.yml]` (or `python docker/driver.py submit [conf.yml]`) will submit a job with parameters specified in conf.yml on both the PS and worker nodes. 
We provide some example ```conf.yml``` in ```FedScale/benchmark/configs``` for each dataset. 
Comments in our example will help you quickly understand how to specify these parameters. 

	+ `fedscale driver stop [job_name]` (or `python docker/driver.py stop [job_name]`)  will terminate the running ```job_name``` (specified in yml) on the used nodes. 

<hr style="border:.8px solid silver">
### Monitor Your Training Progress
 
You can find the job logging `job_name` under the path `log_path` specified in the `conf.yml` file. To check the training loss or test accuracy, you can do:
```
cat job_name_logging |grep 'Training loss'
cat job_name_logging |grep 'FL Testing'
```

We have integrated Tensorboad for the visualization of experiment results. To track the experiment with ```[log_path]``` (e.g., ```./FedScale/benchmark/logs/cifar10/0209_141336```), please try ```tensorboard --logdir=[log_path] --bind_all```, and all the results will be available at: ```http://[ip_of_coordinator]:6006/```.

Meanwhile, all logs are dumped to ```log_path``` (specified in the config file) on each node. 
```testing_perf``` locates at the master node under this path, and the user can load it with ```pickle``` to check the time-to-accuracy performance. The user can also check ```/benchmark/[job_name]_logging``` to see whether the job is moving on.