# Requirements

The most common way for a beginner to run a validator is on a cloud server running Linux. We strongly recommend using a recent Debian Linux OS. For this guide we will be using **Ubuntu 22.04**, but the instructions should be similar for other platforms.

The transaction weights in Creditcoin are benchmarked on reference hardware. We ran the benchmark on a memory optimized `Standard_E4as_v4` VM instance of Azure.

* **CPU**
  * 2nd Generation AMD EPYCTM 7452 (up to 3.35GHz) or 3rd Generation EPYCTM 7763v processors (up to 3.5GHz)
  * 4 vCPUs
* **Storage**
  * 64 GB
* **Memory**
  * 32 GiB RAM
* **System**
  * Ubuntu 22.04 (Linux Kernel 5.16 or newer)

> ![:warning:](https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/atlassian/warning\_32.png)
>
> It is strongly recommended that validators either meet or exceed these hardware specifications in order to ensure that they can process all blocks in time. If you use subpar hardware you will possibly run into performance issues, get less era points, and potentially even get slashed.
