
Script to import data from InfluxDB >=2.0 to VictoriaMetrics.

https://github.com/VictoriaMetrics/vmctl provides similar features for InfluxDB 1.X.

Every unique timeseries is queried one by one and exported to VictoriaMetrics.
For large databases, this might cause too large chunks and some kind of further split 
would be needed.

## Usage

~~~~
./influx_export.py -h
usage: influx_export.py [-h] [--INFLUXDB_V2_ORG INFLUXDB_V2_ORG] [--INFLUXDB_V2_URL INFLUXDB_V2_URL] [--INFLUXDB_V2_TOKEN INFLUXDB_V2_TOKEN]
                        [--INFLUXDB_V2_SSL_CA_CERT INFLUXDB_V2_SSL_CA_CERT] [--INFLUXDB_V2_TIMEOUT INFLUXDB_V2_TIMEOUT] [--INFLUXDB_V2_VERIFY_SSL INFLUXDB_V2_VERIFY_SSL]
                        [--vm-addr VM_ADDR]
                        bucket

Script for exporting InfluxDB data into victoria metrics instance. InfluxDB settings can be defined on command line
or as environment variables (or in .env file  if python-dotenv is installed). 

InfluxDB related args described in https://github.com/influxdata/influxdb-client-python#via-environment-properties

positional arguments:
  bucket                InfluxDB source bucket

optional arguments:
  -h, --help            show this help message and exit
  --INFLUXDB_V2_ORG INFLUXDB_V2_ORG, -o INFLUXDB_V2_ORG
                        InfluxDB organization
  --INFLUXDB_V2_URL INFLUXDB_V2_URL, -u INFLUXDB_V2_URL
                        InfluxDB Server URL, e.g., http://localhost:8086
  --INFLUXDB_V2_TOKEN INFLUXDB_V2_TOKEN, -t INFLUXDB_V2_TOKEN
                        InfluxDB access token.
  --INFLUXDB_V2_SSL_CA_CERT INFLUXDB_V2_SSL_CA_CERT, -S INFLUXDB_V2_SSL_CA_CERT
                        Server SSL Cert
  --INFLUXDB_V2_TIMEOUT INFLUXDB_V2_TIMEOUT, -T INFLUXDB_V2_TIMEOUT
                        InfluxDB timeout
  --INFLUXDB_V2_VERIFY_SSL INFLUXDB_V2_VERIFY_SSL, -V INFLUXDB_V2_VERIFY_SSL
                        Verify SSL CERT.
  --vm-addr VM_ADDR, -a VM_ADDR
                        VictoriaMetrics server
~~~~

Author: Johannes Aalto

SPDX-License-Identifier: Apache-2.0
