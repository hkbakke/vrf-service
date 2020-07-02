# Usage
Add an override.conf that starts a systemd service in a specific VRF. The
service is automatically restarted with the new settings.

Add the `salt-minion` service to the VRF `vrf-management`:

    sudo ./vrf-service vrf-management /lib/systemd/system/salt-minion.service

Remove the `salt-minion` service from any VRFs by using the name `default`:

    sudo ./vrf-service default /lib/systemd/system/salt-minion.service

Use `-t` to test if there will be any changes without actually applying them:

    sudo ./vrf-service -t vrf-management /lib/systemd/system/salt-minion.service

The test command will return exit code 0 if the override file is in the desired
state, and 1 if changes would have been made.
