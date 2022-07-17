---
title: FedScale Leaderboard
permalink: /docs/leader_overview
redirect_from: /docs/leader_overview.html
---

FedScale public leaderboards allow researchers and practitioners to keep track of state-of-the-art methods using a common software stack and a collection of well-defined benchmarks included in FedScale.
This is also a great opportunity to let people know about your work and allow them to compare with it.
We highly encourage you to contribute your official results to the FedScale leaderboards (even if your method was published before the FedScale release). 

Please make sure your experimental protocol follows the rules outlined below, which are inspired by [OGB rules](https://ogb.stanford.edu/docs/leader_overview/) and we found to be reasonable.
We will remove any invalid submissions, so please make sure all the results are correct and reproducible before submitting them. 
Please contact us if there is anything unclear or you have found any problematic submission on the leaderboards. 

<hr style="border:.8px solid silver">

### How Leaderboards Work?
Once you have developed your solution and obtained results, you can submit your test results to our leaderboards. 
For each dataset, we require you to submit the following information.

- **FedScale version**: The FedScale version (e.g., commit id ```256288d```) used to conduct the experiments. 

- **Method**: The name of the method (e.g., name of the proposed algorithm). 

- **External data**: When building your model, indicate whether you use external data (in the form of external pre-trained models, raw text, external unlabeled/labeled data)? If “Yes”, please clearly indicate that in your method name above.

- **Dataset**: The name of an FedScale dataset that you use to evaluate the method.

- **Test performance**: Raw test performance output by FedScale model evaluators, where **average (```torch.mean```) and unbiased standard deviation (```torch.std```) must be taken over 5 different random seeds**. 
You can either not fix random seeds at all, or use the random seeds from 0 to 4. 
We highly discourage you to tune the random seeds. 
For the large FedScale dataset (e.g., Reddit), you only need to use 3 random seeds to report the performance.

- **Contact**: A person's name and email address to contact about the method and code.
The contact author is responsible for addressing any inquiry about their code. 

- **Code**: The Github repository or directory containing all code and configuration to reproduce the result. **A placeholder repository is not allowed.** 
Please add a ```README.md``` file that has detailed instructions (i.e., exact command(s) and the FedScale YAML configuration file) to reproduce the submitted result. 
A good example is [this]().
	
- **Paper**: The original paper describing the method. We recommend an arXiv link; the paper does not need to be peer-reviewed. 

- **Number of parameters**: The number of parameters of your model, which can be calculated by ```sum(p.numel() for p in model.parameters())```. 
This is important for federated learning, where the client device is often resource-constrained.

- **Tuned hyper-parameters**: Please kindly disclose all the hyper-parameters you tuned, and how much you tuned for each of them. 
Please follow the following form: ```"lr: [0.001*, 0.01], num_layers: [4*,5], hidden_channels: [128, 256*], dropout: [0*, 0.5], epochs: early-stop*"```, where the asterisks (*) denote the hyper-parameters you eventually selected (based on validation performance) to report the test performance. 
This information will not appear in the leaderboard for the time being, but it is important for us to keep the record and encourage the fair model selection.

- **Officiality**: Whether the implementation is **official** (implemented by paper authors) or **unofficial** (re-implemented by non-authors).

<!-- 
**To contributors who re-implement existing methods**: Even if you are not the original authors, we still encourage you to contribute your unofficial result to the leaderboards. 
This would be valuable especially when your own implementation of existing methods achieve significantly better performance than the official counterpart (e.g., by running for longer epochs, or by tuning hyper-parameters more carefully). 
Simple tricks can sometimes make methods significantly better! 
If your submission is a non-trivial extension of an exiting method, we encourage you to make it an official submission and write an original technical report. 
Otherwise, please explicitly mention the extension both in the method name and Github README.
 -->

**IMPORTANT:** Accepted submissions may be removed from the leaderboard if any of the required pieces cease to exist; e.g., removing public access to the code repo after acceptance.

<hr style="border:.8px solid silver">

### How to Submit?

Use the [Google form]() to make a submission.

Leaderboards are updated periodically after we check the validity of submission; expect at least a week delay.

<hr style="border:.8px solid silver">

### Explore Leaderboards

- [Computer Vision Tasks]()

- [Natural Language Processing Tasks]()

- [Miscellaneous Tasks]()
