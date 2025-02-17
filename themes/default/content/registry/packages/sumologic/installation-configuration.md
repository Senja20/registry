---
title: Sumo Logic Installation & Configuration
meta_desc: Provides an overview on how to configure credentials for the Pulumi Sumo Logic Provider.
layout: installation
---

The Pulumi Sumo Logic provider uses the Sumo Logic SDK to manage and provision resources.

## Installation

The Sumo Logic provider is available as a package in all Pulumi languages:

* JavaScript/TypeScript: [`@pulumi/sumologic`](https://www.npmjs.com/package/@pulumi/sumologic)
* Python: [`pulumi-sumologic`](https://pypi.org/project/pulumi-sumologic/)
* Go: [`github.com/pulumi/pulumi-sumologic/sdk/go/sumologic`](https://github.com/pulumi/pulumi-sumologic)
* .NET: [`Pulumi.SumoLogic`](https://www.nuget.org/packages/Pulumi.SumoLogic)

## Configuring Credentials

Pulumi relies on the Sumo Logic SDK to authenticate requests from your computer to Sumo Logic. Your credentials are never sent
to pulumi.com.
The Pulumi Sumo Logic Provider needs to be configured with Sumo Logic credentials
before it can be used to create resources.

Once the credentials are obtained, there are two ways to communicate your authorization tokens to Pulumi:

1. Set the environment variables for `SUMOLOGIC_ACCESSID`, `SUMOLOGIC_ACCESSKEY` and `SUMOLOGIC_ENVIRONMENT`:

    ```bash
    $ export SUMOLOGIC_ACCESSID=XXXXXXXXXXXXXX
    $ export SUMOLOGIC_ACCESSKEY=YYYYYYYYYYYYYY
    $ export SUMOLOGIC_ENVIRONMENT=ZZZZZZZZZZZZZZ
    ```

2. Set them using configuration, if you prefer that they be stored alongside your Pulumi stack for easy multi-user access:

    ```bash
    $ pulumi config set sumologic:accessId XXXXXXXXXXXXXX --secret
    $ pulumi config set sumologic:accessKey YYYYYYYYYYYYYY --secret
    $ pulumi config set sumologic:environment ZZZZZZZZZZZZZZ
    ```

Remember to pass `--secret` when setting `sumologic:accessId` and `sumologic:accessKey` so that they are properly encrypted. The complete list of
configuration parameters is in the [Sumo Logic provider README](https://github.com/pulumi/pulumi-sumologic/blob/master/README.md).
