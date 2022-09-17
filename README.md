# Instructions:

**BUG: You still need to do these steps manually:**

- In the CA server `cat ~/easy-rsa/pki/ca.crt`
- In the openvpn server:
  ```cmd
  sudo cp /tmp/ca.crt /usr/local/share/ca-certificates/
  sudo update-ca-certificates
  ```

1. Add node manager public key in the `authorized_keys`
2. `ufw allow ssh`
3. `cp .env.example.json .env.json`
4. `ansible-galaxy collection install community.crypto`
5. Make sure that ansible can connect to the server: `ansible all -m ping -i hosts`
6. Execute your ansible script: `ansible-playbook -i hosts playbook.yml -e @.env.json`

# Read more by yourself:

- [How To Set Up and Configure an OpenVPN Server on CentOS 7](https://www.digitalocean.com/community/tutorials/how-to-set-up-and-configure-an-openvpn-server-on-centos-7)
- [How To Set Up and Configure a Certificate Authority (CA) On Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-set-up-and-configure-a-certificate-authority-ca-on-ubuntu-20-04)
