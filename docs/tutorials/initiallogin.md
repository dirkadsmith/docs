# Initial login in the system

Before getting started with the different parts of the platform, we're going to tackle the very first step of the way: the first time we log in the platform. There are two ways we can log in: through the command line interface \(CLI\) and through the web management interface.

## CLI Login

### Setting your user options

The very first time you log in the system there are some variables that need to be established. They are needed for each interaction, so setting them up before starting lets us omit them in each request. These variables are the **certificate** you received, and the addresses of the **Nalej login server** and the **Nalej API server**. Gather all data \(from the information the Nalej administration provided when signing up for the service\), go to the folder in your computer where you saved the `public-api-cli` executable, and execute the following instructions:

```bash
./public-api-cli options set 
    --key=cacert 
    --value=/Users/youruser/.../certificate.crt

./public-api-cli options set 
    --key=loginAddress 
    --value=login.server.nalej.com

./public-api-cli options set 
    --key=nalejAddress 
    --value=api.server.nalej.com
```

To check if these commands have executed correctly and the options are in fact set, you can use the command:

```bash
./public-api-cli options list
```

By default, the responses to the CLI commands will be JSON-formatted documents. If you want to see them in a format that's easier to read, you should add this other option:

```bash
./public-api-cli options set 
    --key=output 
    --value=text
```

This will return the responses in a more human-readable format. If, however, you happen to need the response of a specific command in a JSON document, just adding --output="JSON" will override this option for that command.

### Login

After this, we can log in normally:

```bash
./public-api-cli login 
    --email=user@nalej.com 
    --password=password
```

## Web Platform login

With a browser, we can go to the login page provided by the Nalej administration team, and use our Nalej user and password to get in the system.

![Login page](../img/tut_login.png)

Once you enter, you can see the platform structure at a glance, and start interacting with it.

### Web interface views

The different views of the system are accessible through the column in the far left part of the screen (with a dark background). The views you can navigate to are:

- **[Organization](../organization/organization-1)**, which contains a view of all members of the organization and its subscription plan.
- **[Infrastructure](infrastructure/inventory)**, where you can interact with the Inventory.
- **[Resources](resources/resources-1)**, where you can manage the clusters in the system, and the nodes associated to them.
- **[Devices](devices/devices-1)**,  where you can see all the devices in the system and the device groups that contain them, and
- **[Applications](applications/applications-1)**, where you can interact with the registered and deployed apps.

For more information on any of these views, please go to the corresponding section of this documentation, where the different views are described in detail.
