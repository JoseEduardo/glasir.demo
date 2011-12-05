Readme for the "env" module.
----------------------------

Purpose
The purpose of the env module is to facilitate the use of a single .ear file (this is known as BigEar mode) for an ATG site. This simplifies deployment.

BigEar
A "big" .ear file contains all code for all deployment configurations, where a configuration is a combination of targets (store, fulfillment, ...) and environments (test, dev, production, ...).

Configuration
To enable a module in a configuration, add it to the ATG-Requires section of the MANIFEST.MF file of the configuration.
E.g. to add "MyAtgModule" to the "env.store.production" configuration, add it to the ATG-Requires line in the file "env/store/production/META-INF/MANIFEST.MF" like this (no quotes): 
"ATG-Required: env.store MyAtgModule"

Launching
To launch an ATG node, use the corresponding env module in the -m parameter to the startDynamo command. 
If env has been properly configured ATG will then launch with only all the required modules.
E.g. "startDynamo -m env.store.production"
