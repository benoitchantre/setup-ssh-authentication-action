# Setup SSH authentication

This action installs your private key and related files in `~/.ssh` to allow an SSH key-based authentication with a remote server.

## Usage

```yaml
- name: Setup SSH key
  uses: benoitchantre/setup-ssh-authentication-action@1.0.0
  with:
    # Private key for connecting to remote hosts.
    # Required.
    private-key: ${{ secrets.PRIVATE_KEY }}

    # Filename of the private key.
    # Optional. Default to `id_rsa`
    private-key-name: id_rsa

    # The SSH configuration. Content of `~/.ssh/config` file.
    # Optional.
    ssh-config: ${{ secrets.SSH_CONFIG }}

    # Content of `~/.ssh/known_hosts` file. The public SSH keys for a
    # host may be obtained using the utility `ssh-keyscan`.
    # Required.
    known-hosts: ${{ secrets.KNOWN_HOSTS }}
```
You can use run this action multiple times to install more than one key as long as you use different key names.

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE).
