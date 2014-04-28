# Deployment

Deployment for most code at MCPH uses our proprietary Patchwork daemon. The daemon is fairly slim, leaving most responsibility up to the shell scripts defined in the repository itself, for maximum flexibility throughout the process.

Repositories which use Patchwork must have a `/.patchwork` directory. This must have the following structure:

```
.patchwork
   |-- repo.json
   |-- build.sh
   |-- deploy.sh
   +-- upgrade
      |-- v1.1.sh
      |-- v0.9.sh
```

 * `repo.json` See the format below:

```
{
    "version": "someversion2.0", // Any valid filename works! Used for upgrading (see below)
    "targets": ["127.0.0.1", "google.com"] // List of hostnames corresponding to the master's config
}
```

 * `build.sh` This is a shell script that is executed each time before repository deployment. The current working directory is set to the repository's root. This is executed on the *deployment server* prior to sending it to every target server.
 * `deploy.sh` This script is executed by the *target server*. The current working directory is set to the repository's root. This should copy necessary files from the repository to the server, restart services, etc.
 * `upgrade/*` Contains scripts that should be run on *target servers* in order to complete an upgrade. If a shell script exists which matches the "version" given in repo.json, then it will be executed.

> Note: ensure that the version is updated with each new merge or commit into master. Otherwise, upgrade scripts may be run multiple times with undesirable effects.

The process of the servers which you need to be concerned about can be summed up thusly:

 1. Clone the repository to the deployment server.
 2. Check for existence of `.patchwork/build.sh`, and execute it if it does exist.
 3. Compress the repository folder, and send it to each target server. Remove the cloned repository.
 4. Receive the compressed folder on the target servers. Unzip it to a temporary directory.
 5. Execute the appropriate upgrade script, if one exists.
 6. Execute the `.patchwork/deploy.sh`, then remove the temporary zip and repo.