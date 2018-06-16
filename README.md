# LookingGlass-En

This LookingGlass is Powered by [LookingGlass](https://github.com/telephone/LookingGlass) and Localized by [LookingGlass](https://github.com/ILLKX/LookingGlass-En).  

## Demo
[https://lgen.illkx.tk](https://lgen.illkx.tk)  

## Some modifications after forking  
1、Add GeoIP data when traceroute under IPv4    
2、Use DD command to create test files  
3、Add translation for simplified Chinese  
4、Modify the output language of traceroute result  

## Screenshot

![](https://github.com/ILLKX/LookingGlass-En/raw/master/screenshot.jpg)

## Overview

LookingGlass is a user-friendly PHP based looking glass that allows the public (via a web interface) to execute network
commands on behalf of your server.

Current version: v1.3.0

It's recommended that everyone updates their existing install!

## Features

* Automated install via bash script
* IPv4 & IPv6 support
* Live output via long polling
* Multiple themes
* Rate limiting of network commands

## Implemented commands

* host
* mtr
* mtr6 (IPv6)
* ping
* ping6 (IPv6)
* traceroute
* traceroute6 (IPv6)

__IPv6 commands will only work if your server has external IPv6 setup (or tunneled)__

## Requirements

* PHP >= 5.3
* PHP PDO with SQLite driver (required for rate-limit)
* SSH/Terminal access (able to install commands/functions if non-existent)

## Install

1. Download [LookingGlass](https://github.com/ILLKX/LookingGlass/archive/master.zip) to the intended
folder within your web directory
2. Extract archive:
    - Extract archive to the current directory:
        - `unzip master.zip`
3. Navigate to the `LookingGlass` subdirectory in terminal
4. Run `bash configure.sh`
5. Follow the instructions and `configure.sh` will take care of the rest

_Forgot a setting? Simply run the `configure.sh` script again_

## Updating

1. Download [LookingGlass](https://github.com/telephone/LookingGlass/archive/v1.3.0.tar.gz) to the folder containing
your existing install
2. Extract archive: `tar -zxvf LookingGlass-1.3.0.tar.gz --overwrite --strip-components 1`
    - This will overwrite/update existing files
3. Navigate to the `LookingGlass` subdirectory in terminal
4. Run `bash configure.sh`
5. Follow the instructions and `configure.sh` will take care of the rest
    - Note: Re-enter test files to create random test files from `GNU shred`

_Forgot a setting? Simply run the `configure.sh` script again_

## Apache

An .htaccess is included which protects the rate-limit database, disables indexes, and disables gzip on test files.
Ensure `AllowOverride` is on for .htaccess to take effect.

Output buffering __should__ work by default.

For an HTTPS setup, please visit:
- [Mozilla SSL Configuration Generator](https://mozilla.github.io/server-side-tls/ssl-config-generator/)

## Nginx

To enable output buffering, and disable gzip on test files please refer to the provided configuration:

[HTTP setup](LookingGlass/lookingglass-http.nginx.conf)

The provided config is setup for LookingGlass to be on a subdomain/domain root.

For an HTTPS setup please visit:
- [Best nginx configuration for security](http://tautt.com/best-nginx-configuration-for-security/)
- [Mozilla SSL Configuration Generator](https://mozilla.github.io/server-side-tls/ssl-config-generator/)

## License

Code is licensed under MIT Public License.

* If you wish to support my efforts, keep the "Powered by LookingGlass" link intact.
