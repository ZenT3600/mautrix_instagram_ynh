# A Matrix-Instagram puppeting bridge for YunoHost

> *This package allows you to install a Mautrix-Instagram bridge quickly and simply on a YunoHost server alongside Matrix-Synapse.  
If you don't have YunoHost, please see [here](https://yunohost.org/#/install) to know how to install and enjoy it.*

## Overview
A puppeting bridge between Matrix and Instagram packaged as a YunoHost service. Messages, media and notifications are bridged between a instagram user and a matrix user. The matrix user can invite other matrix user in a bridged whatsapp room, such that even people without a instagram account can participate to insagram group conversations. The ["mautrix-instagram"](https://github.com/tulir/mautrix-instagram/wiki) bridge consists in a synapse app service and relies on postgresql. Therefore, [Synapse for YunoHost](https://github.com/YunoHost-Apps/synapse_ynh) should be installed beforehand.

**Shipped version:** 0.1.5

## Screenshots

![](Link to an screenshot for this app)

## Demo

* Contact hello@navan.dev.

## Bridging usage
### Bridge a Instagram user and a Matrix user
* First your matrix user or server has to be authorized in the bridge configuration (see below)
* Then, invite the bot (default @instagrambot:yoursynapse.domain) in this new matrix-instagram bot administration room.
* Type ``login``
* Send ``help`` to the bot in the created room to know how to control the bot.
See also [upstream wiki Authentication page](https://github.com/tulir/mautrix-instagram/wiki/Authentication)

** Note that several Instagram and Matrix users can be bridged, each Instagram account has its own bot administration room. If they are in a same Instagram group, only one matrix room will be created. **

## Configuration of the bridge

The bridge is roughly configured at installation, e.g. allowed admin and user of the bot. Finer configuration can be done by modifying the
following configuration file with SSH: 
```/opt/yunohost/mautrix_instagram/config.yaml```
and then restarting the mautrix_instagram service.

## Documentation

 * Official "mautrix-instagram" documentation: https://github.com/tulir/mautrix-instagram/wiki
 * Matrix room (matrix bridges in Yunohost): #mautrix_yunohost:matrix.fdn.fr
 * Matrix room (upstream app): #instagram:maunium.net
 * YunoHost documentation: If more specific documentation is needed, feel free to contribute.

## YunoHost specific features

#### Multi-users support

* Bot users are not related to Yunohost users. Any matrix account or server autorized in the configuration of the bridge can use the bot. 
* The instagrambot is a local matrix-synapse user, but accessible through federation (synapse public or private).
* Several Instagram and Matrix users can be bridged with one bridge, each user has its own bot administration room. 

#### Supported architectures

* Tested on ARMv7 in Feb 2021

