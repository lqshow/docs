---
type: docs
title: "rad credential register azure CLI reference"
linkTitle: "rad credential register azure"
slug: rad_credential_register_azure
url: /reference/cli/rad_credential_register_azure/
description: "Details on the rad credential register azure Radius CLI command"
---
## rad credential register azure

Register (Add or update) Azure cloud provider credential for a Radius installation.

### Synopsis

Register (Add or update) Azure cloud provider credential for a Radius installation..

This command is intended for scripting or advanced use-cases. See 'rad init' for a user-friendly way
to configure these settings.

Radius will use the provided service principal for all interactions with Azure, including Bicep deployment, 
Radius Environments, and Radius portable resources. 

Radius will use the provided subscription and resource group as the default target scope for Bicep deployment.
The provided service principal must have the Contributor or Owner role assigned for the provided resource group
in order to create or manage resources contained in the group. The resource group should be created before
calling 'rad credential register azure'.


Radius cloud providers enable Radius Environments to deploy and integrate with cloud resources (Azure, AWS).
The Radius control-plane stores credentials for use when accessing cloud resources.

Cloud providers are configured per-Radius-installation. Configuration commands will use the current workspace
or the workspace specified by '--workspace' to configure Radius. Modifications to cloud provider configuration
or credentials will affect all Radius Environments and applications of the affected installation.

```
rad credential register azure [flags]
```

### Examples

```

# Register (Add or update) cloud provider credential for Azure with service principal authentication
rad credential register azure --client-id <client id/app id> --client-secret <client secret/password> --tenant-id <tenant id>

```

### Options

```
      --client-id string       The client id or app id of an Azure service principal.
      --client-secret string   The client secret or password of an Azure service principal.
  -h, --help                   help for azure
  -o, --output string          output format (supported formats are json, table) (default "table")
      --tenant-id string       The tenant id of an Azure service principal.
  -w, --workspace string       The workspace name
```

### Options inherited from parent commands

```
      --config string   config file (default "$HOME/.rad/config.yaml")
```

### SEE ALSO

* [rad credential register]({{< ref rad_credential_register.md >}})	 - Register(Add or update) cloud provider credential for a Radius installation.

