# Network-Slicing-Aether

## Things done differently

* Sim start & end range must be there in the simapp section, and later can be configured in aether roc dasboard.
* different ip domain needs to be added.
* Changed the makefile for multiple upf support.
* Added different file for monitoring.
* multiple upf endpoints should be there.

## Deployment

```bash
cd Network-Slicing-Aether
```

```bash
make node-prep
```

Once the cluster is up and running:

For running afpacket mode directly run the following command. For running aiab in dpdk mode first set up dpdk and sriov and then run the below command. For dpdk refer to the following [repo](https://github.com/NgKore47/SD-Core-DPDK)

```bash
ENABLE_GNBSIM=false DATA_IFACE=ens1f0 CHARTS=latest make 5g-core roc-5g-models
```

Once every pod is up then create multiple upf:

```bash
ENABLE_GNBSIM=false DATA_IFACE=ens1f0 CHARTS=latest make 5g-upf
```
Run this command the number of times you want to create upf.

Now access the dashboard using `ip` & port `31194`.

Now, change the things in dashboards