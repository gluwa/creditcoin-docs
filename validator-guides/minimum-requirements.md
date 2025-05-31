# Minimum Requirements

The most common way for a beginner to run a validator is on a cloud server running Linux. We strongly recommend using a recent Debian Linux OS. For this guide we will be using **Ubuntu 22.04**, but the instructions should be similar for other platforms.

{% hint style="danger" %}
Creditcoin does not currently support Macs using Apple silicon, such as the M1 and M2
{% endhint %}

* **CPU**
  * Intel Core i5-8400 or better
    * 6 Cores @ 2.8Ghz
    * 9M Cache
* **Storage**
  * Needs to be sufficient for targeted chain
  * 256G + recommended for CC3 mainnet as of 2025-05-01
* **Memory**
  * 8GB
* **System**
  * Ubuntu 22.04 (Linux Kernel 5.16 or newer)
* **Tokens**
  * The minimum stake required to run a validator is currently 1000 CTC



> <img src="https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/atlassian/warning_32.png" alt=":warning:" data-size="original">
>
> It is strongly recommended that validators either meet or exceed these hardware specifications in order to ensure that they can process all blocks in time. If you use subpar hardware you will possibly run into performance issues, get less era points, and potentially even get slashed.

The transaction weights in Creditcoin are benchmarked on reference hardware. We ran the benchmark on a memory optimized `Standard_E4as_v4` VM instance of Azure.
