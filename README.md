# trading-peripheral #

<!-- Python script that exports Hyper SBI 2 watchlists to Yahoo
Finance and extracts order status from SBI Securities web page -->

<!-- hypersbi2 python chrome selenium webdrivermanager pandas
google-api -->

A `trading_peripheral.py` Python script:

  * replaces watchlists on the SBI Securities website with [Hyper SBI
    2](https://go.sbisec.co.jp/lp/lp_hyper_sbi2_211112.html)
    watchlists
  * exports them from the `%APPDATA%\SBI
    Securities\HYPERSBI2\IDENTIFIER\portfolio.json` file to [My
    Portfolio](https://finance.yahoo.com/portfolios) on Yahoo Finance
  * extracts order status from the SBI Securities web page and copies
    them to the clipboard
  * (optional) retrieves SBI Securities maintenance schedules and
    inserts them into Google Calendar

> **Warning** This script is currently under heavy development.
> Changes in functionality can occur at any time.

## Prerequisites ##

This script has been tested in [Python for
Windows](https://www.python.org/downloads/windows/) with Hyper SBI 2
and uses the following web browser and packages:

  * [Chrome](https://www.google.com/chrome/) authenticates to the
    website and loads the page
  * [Selenium
    WebDriver](https://www.selenium.dev/documentation/webdriver/)
    drives a browser
  * [Webdriver Manager for
    Python](https://github.com/SergeyPirogov/webdriver_manager)
    automatically updates the driver
  * [pandas](https://pandas.pydata.org/) to extract data from the web
    pages
  * (optional)
    [google-api-python-client](https://googleapis.github.io/google-api-python-client/docs/),
    [google-auth-httplib2](https://github.com/googleapis/google-auth-library-python-httplib2),
    and
    [google-auth-oauthlib](https://github.com/googleapis/google-auth-library-python-oauthlib)
    to access to Google APIs

Install each package as needed.  For example:

``` powershell
winget install Google.Chrome
pip install selenium
pip install webdriver-manager
pip install pandas
```

## Usage ##

If you are using Chrome as your default web browser, create a separate
profile that stores your credentials and specify it as the value of
the `profile_directory` option as follows:

``` powershell
py trading_peripheral.py -G
```

A `%LOCALAPPDATA%\trading-peripheral\trading_peripheral.ini`
configuration file saves these configurations.

### Options ###

  * `-p`: backup Hyper SBI 2 `portfolio.json`
  * `-s`: replace watchlists on the SBI Securities website with Hyper
    SBI 2 watchlists
  * `-y`: export Hyper SBI 2 `portfolio.json` to My Portfolio on Yahoo
    Finance
  * `-o`: extract order status from the SBI Securities web page and
    copy them to the clipboard
  * `-m`: insert maintenance schedules into Google Calendar
  * `-G`: configure general options and exit
  * `-O`: configure order state formats and exit
  * `-A`: configure actions and exit

## Known Issues ##

  * It appears that Yahoo Finance does not have stocks listed solely
    on the Nagoya Stock Exchange.
  * Extracting order status assumes day trading on margin.

## License ##

[MIT](LICENSE.md)

## Link ##

  * [*Python Scripting to Export Hyper SBI 2 Watchlists to Yahoo
    Finance*](https://carmine560.blogspot.com/2023/02/python-scripting-to-export-hyper-sbi-2.html):
    a blog post for more details
