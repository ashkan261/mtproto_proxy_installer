# MTProto Proxy Installer

## Overview
This is an automatic interactive installer for **MTProto Proxy**, based on the original implementation available at [seriyps/mtproto_proxy](https://github.com/seriyps/mtproto_proxy).

## Supported Operating Systems
- **Ubuntu** `18.xx - 30.xx`
- **Debian** `8 - 11`
- **CentOS** `7`

## Installation
To install **MTProto Proxy** on your server, use the following command:

```sh
curl -L -o mtp_install.sh https://raw.githubusercontent.com/ashkan261/mtproto_proxy_installer/main/mtp_install.sh && 
bash mtp_install.sh -p <port> -s <secret> -t <ad tag> -a dd -a tls -d <fake-tls domain>
```

Replace the placeholders with the desired values:
- `<port>`: Proxy port (e.g., `2083`)
- `<secret>`: Secret key for authentication
- `<ad tag>`: Advertisement tag from **@MTProxybot**
- `<fake-tls domain>`: A fake TLS domain (e.g., `docs.google.com`)

## Updating the Proxy
To **upgrade** to the latest version while keeping your existing configuration, run:

```sh
bash mtp_install.sh upgrade
```

## Configuration Management
To **reconfigure the proxy interactively**, use:

```sh
bash mtp_install.sh reconfigure -p <port> -s <secret> -t <ad tag> -a dd -a tls -d <fake-tls domain>
```

To **reload proxy settings** after making manual changes, run:

```sh
bash mtp_install.sh reload
```

## Logs and Monitoring
Logs are stored in:

```sh
/var/log/mtproto-proxy/application.log
```

## Troubleshooting
If you encounter any issues:
1. Ensure that your server meets the system requirements.
2. Verify that required dependencies (`erlang-nox`, `make`, `sed`, `tar`) are installed.
3. Check firewall settings to allow traffic on the specified port.
4. Review logs for error messages and debugging information.

## License
This project follows the **MIT License**. See the original repository for more details.

## Credits
- Original implementation: [seriyps/mtproto_proxy](https://github.com/seriyps/mtproto_proxy)
- Modified for broader OS support and easier installation.
