# IPATool
[![Release](https://img.shields.io/github/release/majd/ipatool.svg?label=Release)](https://GitHub.com/majd/ipatool/releases/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/majd/ipatool/blob/main/LICENSE)
[![Unit Tests](https://github.com/majd/ipatool/actions/workflows/unit-tests.yml/badge.svg)](https://github.com/majd/ipatool/actions/workflows/unit-tests.yml)
[![Integration Tests](https://github.com/majd/ipatool/actions/workflows/integration-tests.yml/badge.svg)](https://github.com/majd/ipatool/actions/workflows/integration-tests.yml)
![Swift](https://img.shields.io/badge/Swift-5.5-green.svg)
![macOS](https://img.shields.io/badge/macOS-10.15%2B-green.svg)

`ipatool` is a command line tool that allows you to search for iOS apps on the [App Store](https://apps.apple.com) and download a copy of the app package, known as an _ipa_ file.

![Demo](./demo.gif)

* [Requirements](#requirements)
* [Installation](#installation)
  * [Manual](#manual)
  * [Homebrew](#homebrew)
* [Usage](#usage)
* [FAQ](https://github.com/majd/ipatool/wiki/FAQ)
* [License](#license)

## Requirements
* macOS 10.15 or later.
* Apple ID set up to use the App Store.

## Installation

### Manual

You can grab the latest version of `ipatool` from [GitHub releases](https://github.com/majd/ipatool/releases).

### Homebrew

You can install `ipatool` using [Homebrew](https://brew.sh).

```
$ brew tap majd/repo
$ brew install ipatool
```

## Usage

To search for apps on the App Store, use the `search` command.

```
OVERVIEW: Search for iOS apps available on the App Store.

USAGE: ipatool search <term> [--limit <limit>] [--country <country>] [--device-family <device-family>] [--log-level <log-level>]

ARGUMENTS:
  <term>                  The term to search for. 

OPTIONS:
  -l, --limit <limit>     The maximum amount of search results to retrieve.
                          (default: 5)
  -c, --country <country> The two-letter (ISO 3166-1 alpha-2) country code for
                          the iTunes Store. (default: US)
  -d, --device-family <device-family>
                          The device family to limit the search query to.
                          (default: iPhone)
  --log-level <log-level> The log level. (default: info)
  --version               Show the version.
  -h, --help              Show help information.
```

To download a copy of the ipa file, use the `download` command.

```
OVERVIEW: Download (encrypted) iOS app packages from the App Store.

USAGE: ipatool download --bundle-identifier <bundle-identifier> [--email <email>] [--password <password>] [--auth-code <auth-code>] [--country <country>] [--device-family <device-family>] [--log-level <log-level>]

OPTIONS:
  -b, --bundle-identifier <bundle-identifier>
                          The bundle identifier of the target iOS app. 
  -e, --email <email>     The email address for the Apple ID. 
  -p, --password <password>
                          The password for the Apple ID. 
  --auth-code <auth-code> The 2FA code for the Apple ID. 
  -c, --country <country> The two-letter (ISO 3166-1 alpha-2) country code for the iTunes Store. (default: US)
  -d, --device-family <device-family>
                          The device family to limit the search query to. (default: iPhone)
  --log-level <log-level> The log level. (default: info)
  --version               Show the version.
  -h, --help              Show help information.
```

**Note:** You can specify the Apple ID email address and username as arguments when using the tool or by setting them as environment variables (`IPATOOL_EMAIL` and `IPATOOL_PASSWORD`). If you do not specify this information using either of those methods, the tool will prompt for user input in an interactive session. Similarly, you can supply the 2FA code interactively or using the environment variable `IPATOOL_2FA_CODE`.

## License

IPATool is released under the [MIT license](https://github.com/majd/ipatool/blob/main/LICENSE).