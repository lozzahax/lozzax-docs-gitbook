# 🏎 Express service node setup guide

The guide below will help you configure a device with the Lozzax service_node, and stake $LOZZAX to register the node on the Lozzax network.

> Note: This guide assumes some familiarity with the  command line and running a server. For a more detailed walkthrough, check out our [full service node setup guide](full-service-node-setup-guide.md).

### Operating system requirements

One of:

* Ubuntu 18.04 \("bionic"\)
* Ubuntu 20.04 \("focal"\)
* Ubuntu 20.10 \("groovy"\)

> Note: There are strict uptime requirements for service nodes \(see [Service Node deregistration](service-node-deregistration.md)\). It is **not recommended** to run a service node on a personal device or any device which will not be constantly online. We recommend running your service node on a VPS with a reliable provider.

### Firewall Configuration

If you are using a firewall then ensure that the following ports are open/reachable

* Port 22120 \(storage server to storage server\)
* Port 22121 \(client to storage server\)
* Port 22122 \(blockchain syncing\)
* Port 22125 \(service node to service node\)
* Port 1090 \(UDP, not TCP, unlike all of the above; lokinet router data\)

### Ultra-express guide

You can configure a new Lozzax Service Node by running the following 4 commands on the Linux server you want to become a service node \(these commands will work on Ubuntu; modifications may be necessary on other Linux distributions\):

```text
wget https://github.com/lozzax/lozzax/releases/download/v9.2.0/storage.tar.gz

tar -xvf storage.tar.gz

cd storage/


```

The best way to run the lozzax servie_node is to use this method below for now

```text
./lozzax-storage 0.0.0.0 8080 --omq-port 21020 --lozzaxd-rpc=tcp://127.0.0.1:33129
```

Remember to use this `tcp://127.0.0.1:33129` when running the `lozzaxd` daemon


Congratulations! Your service node is now ready to be registered and staked.

### Staking your service node

#### Preparing your service node for registration

Run he load daemon like his 

```text
./lozzaxd --service-node  --service-node-public-ip YOUR-IP-ADDRESS --lmq-local-control=tcp://127.0.0.1:33129
```

To prepare your service node for registration, run the following command were you have `lozzaxd` running:

```text
prepare_registration
```

This will prompt you for some registration details, then output a registration command. Copy the output from this command in preparation for the next step.

> Note: You can safely run this command multiple times if you change your mind about some of the registration questions before you submit the registration.

#### Staking and registering your service node

To stake and register your service node, open the Lozzax GUI wallet. Make sure your wallet has a balance of at least 25,000 $LOZZAX to meet the service node staking requirement \(less if you're configuring a [shared service node](full-service-node-setup-guide.md#5-2-setting-up-a-pooled-service-node)\). Navigate to the `Service Nodes`tab &gt; `Registration` section, and paste the output from the above command, then click **Register Service Node**. 

Done! Your staking transaction will now be submitted to the network, and after a short delay, your service node will be registered and begin contributing to the network \(and receiving rewards!\).

#### Checking registration status

You can easily check if your service node is registered on the network. First, connect to the VPS where the service node is running and run the following command to retrieve your service node's public key:

```text
 status
```

This will output a bunch of information about your service node, but there's one part we're interested in at this stage: The long string of random letters and numbers after the characters `SN:` . This string is your service node's public key, used to identify your service node on the list of registered and operational service nodes. Select and copy the public key \(do not copy any of the surrounding information\).

You can now jump onto [explorer.lozzax.xyz](https://explorer.lozzax.xyz/), open the full list of active service nodes, and use Cmd+F/Ctrl+F to check if your service node's public key appears in the list.

Having trouble? Just [head to our Support section](../../support.md).

