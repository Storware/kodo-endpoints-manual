# Server upgrade

When the new KODO for Endpoints server upgrade package is available it is uploaded to the Storware repository server \(`http://repo.storware.eu/kodo-endpoints`\). 

To do the KODO server upgrade, do the following steps:

1. Login to the shell as the `kodo` user.
2. Use `sudo` command to run a shell with `root` privileges:

   ```text
   #sudo -s
   ```

   Asked for a password use the `kodo` user password.

3. Use the `dnf clean all` command to clean information about cached packages.
4. Before updating the KODO for Endpoints server, the operating system must be updated. To do this, execute the following command.

   ```
   # dnf -y update
   ```

5. Next, to update the KODO for Endpoints server, execute the following command: 

   ```
   # yum update kodo-for-endpoints
   ```

6. If the command was executed successfully and the proces is completed, the KODO server has to be restarted. To do this, do as follow:
   1. Switch to the `kodo` user:

      ```
       #su kodo
      ```

   2. Go to the `/opt/storware/kodo-server/api-core/bin/` directory

      ```
       $ cd /opt/storware/kodo-server/api-core/bin/
      ```

   3. Execute the script `stop.sh` and then `start.sh`. You can also check the server status:

      ```
      $ ./stop.sh
      Stopping API (pid:1432)....
      $./start.sh
      Starting API (pid:1373).....
      $./status.sh
      API (pid:1373) running.
      ```
7. Now you can log in again to the KODO for Endpoint UI. 

