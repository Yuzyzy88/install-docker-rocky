# Install Docker on Rocky 9

1. Uninstall Old Versions
   ```
   sudo dnf remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine \
                  podman \
                  runc
   ```

2. Set Up Repository
   ```
   sudo dnf -y install dnf-plugins-core
   sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
   ```

3. Install Docker
```
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

4. Enable Docker
```
sudo systemctl enable --now docker
sudo systemctl status docker
```

5. Add Local User to Docker Group
   ```
   usermod -aG docker $USER
   ```
