# Usage
Add an override.conf that starts a systemd service in a specific VRF. The
service is automatically restarted with the new settings.

Add the `salt-minion` service to the VRF `vrf-management`:

    sudo ./vrf-service -v vrf-management /lib/systemd/system/salt-minion.service

Remove the `salt-minion` service from any VRFs by leaving out the `-v` option:

    sudo ./vrf-service /lib/systemd/system/salt-minion.service

Use `-t` to test if there will be any changes without actually applying them:

    sudo ./vrf-service -t -v vrf-management /lib/systemd/system/salt-minion.service
