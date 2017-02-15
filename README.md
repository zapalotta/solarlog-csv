# solarlog-csv
A python package for creating csv-files from data generated by [Solar-Log](http://www.solar-log.com/en/home.html) devices.  

The csv-files generated are structured per inverter per year. A UNIX-timestamp collumn is added for ease of import in databases etc.
## Requirements
- pip3 ([installation instructions](https://pip.pypa.io/en/stable/installing))
- Python3

## Install

    sudo pip3 install git+https://github.com/MikiDi/solarlog-csv.git


## Usage
1. Download all your `min*.js`-files from the Solar-Log ftp-server. The address of the Solar-Log server you are registered on is the same as the address you use to access the online dashboard.

        mkdir solarlog-download
        cd solarlog-download
        wget ftp://username:password@solarlog-server.eu/min*.js

2. Run solarlog-csv

        solarlog-csv ./path/to/solarlog-download 'Europe/Brussels'

  *note: Because the timestamps provided by Solar-Log are local you should make sure to also provide your timezone for the conversion to UNIX-timestamp to work correctly
  (supported timezones in TZ collumn of [Wikipedia table of timezones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones))*

## Example data
An example of a min.js file can be found here: [min120515.js](https://github.com/MikiDi/solarlog-csv/blob/master/example/min120515.js)

Excerpt from a generated csv-file:

    timestamp,localtime,Pac,Pdc,Eday,Udc
    1357056000,01.01.13 17:00:00,0,0,929,307
    1357055760,01.01.13 16:56:00,0,0,929,381
    1357055400,01.01.13 16:50:00,0,0,929,403

## Supported devices
Tested with Solar-Log 500
