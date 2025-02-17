# Setup New relic clients

* [x] Get the installation script for your OS

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption><p>New Relic - Setup with Guided install</p></figcaption></figure>

* [x] Generate script to deploy the monitoring agent

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption><p>Get Install script to deploy the newrelic agent</p></figcaption></figure>

* [x] Get the command line to launch the agent's setup

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

* [x] Run the script on your vm

{% hint style="info" %}
* Prefer to use the sudo command with your current user as the root account
* Curl, sudo are prerequisites to be installed before running the script&#x20;
{% endhint %}

```
[INPUT]
curl -Ls https://download.newrelic.com/install/newrelic-cli/scripts/install.sh | `
bash && sudo  NEW_RELIC_API_KEY=<yourApiKey> NEW_RELIC_ACCOUNT_ID=<yourId> /usr/local/bin/newrelic install

[OUTPUT]
Starting installation.
Installing New Relic CLI v0.67.27
Installing to /usr/local/bin

 _   _                 ____      _ _
| \ | | _____      __ |  _ \ ___| (_) ___
|  \| |/ _ \ \ /\ / / | |_) / _ | | |/ __|
| |\  |  __/\ V  V /  |  _ |  __| | | (__
|_| \_|\___| \_/\_/   |_| \_\___|_|_|\___|

Welcome to New Relic. Let's set up full stack observability for your environment.

◢ Connecting to New Relic Platform..

[...]
Reading package lists...
Running agent status check attempt...
Agent status check ok.
Infra key: debian-projwebbdd
✔ Installing Infrastructure Agent
   Installed

  New Relic installation complete
```

* [x] Install Golden Signal Alerts and the Agent

```bash
==> Installing Golden Signal Alerts
Creating alert policy Golden Signals...
done
Adding alert condition High CPU...
done
Adding alert condition High Application Error percentage...
done
Adding alert condition High Application Response Time...
done
Adding alert condition Low Application Throughput...
done
Would you like to be notified on your registered email address nicolas.glassey@cpnv.ch when this alert triggers Y/N (default: N)? Y

Notification channel not found for email address xxxx.xxxx@cpnv.ch, creating notification channel...
level=fatal msg="unexpected end of JSON input"
done
✔ Installing Golden Signal Alerts
   Installed

  New Relic installation complete

  --------------------
  Installation Summary

  ✔  Golden Signal Alerts  (installed)
  ✔  Infrastructure Agent  (installed)

  View your data at the link below:
  ⮕  https://onenr.io/0qQabV116w1
```

 ![image-20230512112016837](./assets/image-20230512112016837.png)

* [x] See your data (after the installation)

  https://onenr.io/0BQr68bV3QZ -> to observe the data

  ![image-20230512140417256](./assets/image-20230512140417256.png)

* [x] Observe the Dashboard displaying your vm's

  ![image-20230512140138973](./assets/image-20230512140138973.png)

* [x] Repeat this process for your Windows Vm.
