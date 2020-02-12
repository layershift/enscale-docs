---
title: 'Transfer environment ownership'
taxonomy:
    category:
        - docs
visible: true
---

Enscale allows for the possibility of environments to be transferred between paid Enscale accounts. This feature comes in most handy if you're a developer and you need a simple and easy way to hand off a final project to your client so they can continue paying for it.

Transferring an environment will leave all environment configurations in place and there is absolutely no downtime. 

### Transfer to a different user

To transfer environment ownership, all you need to do is Enter the environment, select **Transfer environment** from the **Actions** drop-down menu.
[]

Enter the email address of the user you want to transfer to.
[]

!!! The receiving party will need to have an upgraded Enscale account, else the transfer will fail.

While the request is pending, you will see a **Transferring** icon next to the environment name. You can click it to see details of your transfer request or to cancel the request.

Once the request is approved, the environment will be removed from your account and all collaboration on the specific environment will be cancelled.

### Accept an incoming transfer

If someone wants to transfer an environment to your account, you will receive an email requesting approval to proceed with the transfer.

!!! Always make sure the request is from someone trusted! When you accept an environment to be transferred to your account, you assume responsibility for said environment contents as well agree to be charged for its resource requirements.

Once you accept the request, the environment will immediately be transferred to your account in the same state (stopped/started) and without any configuration changes.

For security reasons the environment will not have any collaborators regardless of collaboration permissions on the original account, so please make sure to [share the environment](https://enscale.com/docs/10/features/collaboration#step-3-sharing-environments) with the appropriate collaborators.