---
title: Ship Linux logs
logo:
  logofile: linux.svg
  orientation: vertical
data-source: Linux
contributors:
  - imnotashrimp
shipping-tags:
  - os
---

## Setup

<details>

<summary>
Configuration tl;dr
</summary>

| Item | Description |
|---|---|
| Files | [Sample configuration](https://raw.githubusercontent.com/logzio/logz-docs/master/shipping-config-samples/logz-rsyslog-config.conf) |
| Listener | Port 5000. For help finding your region's listener host, see [Account region]({{site.baseurl}}/user-guide/accounts/account-region.html). |
| Default log location | `/var/log/` |
| Log type _\(for preconfigured parsing\)_ | `syslog` |
{:.paramlist}

</details>

#### Guided configuration

**Before you begin, you'll need**:
root access

<div class="tasklist">

##### Run the rsyslog configuration script

{% include log-shipping/replace-vars.html token=true listener=true %}

```shell
curl -sLO https://github.com/logzio/logzio-shipper/raw/master/dist/logzio-rsyslog.tar.gz \
  && tar xzf logzio-rsyslog.tar.gz \
  && sudo rsyslog/install.sh -t linux -a "<<SHIPPING-TOKEN>>" -l "<<LISTENER-HOST>>"
```

##### Check Logz.io for your logs

Give your logs some time to get from your system to ours, and then [open Kibana](https://app.logz.io/#/dashboard/kibana).

If you still don't see your logs, see [log shipping troubleshooting]({{site.baseurl}}/user-guide/log-shipping/log-shipping-troubleshooting.html).

</div>