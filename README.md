# Usage
Add an override.conf that starts a systemd service in a specific VRF. The
service is automatically restarted with the new settings.

    sudo ./vrf-service /lib/systemd/system/salt-minion.service vrf-management
