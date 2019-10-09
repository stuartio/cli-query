[![Build Status](https://travis-ci.com/aalquist/cli-query.svg?branch=master)](https://travis-ci.com/aalquist/cli-query)

# cli-query
CLI-Query is a command line interface indended to simplify the interaction of multiple API endpoints available on [developer.akamai.com](https://developer.akamai.com/). 

## sample install

First install [Akamai CLI](https://developer.akamai.com/cli/docs/getting-started), then run:

```
akamai install https://github.com/aalquist/cli-query

```


## Help Text

``` 
usage: akamai query help [command] [--version]
                                   {help,filtertemplate,bulksearchtemplate,ldslist,netstoragelist,netstorageuser,groupcpcodelist,bulksearch}
                                   ...

Akamai Query CLI

positional arguments:
  {help,filtertemplate,bulksearchtemplate,ldslist,netstoragelist,netstorageuser,groupcpcodelist,bulksearch}
                        commands
    help                Show available help
    filtertemplate      prints a filter template
    bulksearchtemplate  prints a bulksearch template
    ldslist             List all cpcode based log delivery configurations
    netstoragelist      List storage groups
    netstorageuser      List netstorage users
    groupcpcodelist     CPCODES assigned to groups
    bulksearch          bulk search property manager configurations

optional arguments:
  --version             show program's version number and exit

``` 
## Querying Log Delivery Service (LDS)

``` 
usage: akamai query [command] ldslist [--show-json] [--use-filterstdin]
                                      [--file FILE] [--template TEMPLATE]
                                      [--edgerc EDGERC] [--section SECTION]
                                      [--debug] [--account-key ACCOUNT_KEY]

optional arguments:
  --show-json           output json
  --use-filterstdin     use stdin for query
  --file FILE           the json file for query
  --template TEMPLATE   use template name for query
  --edgerc EDGERC       Location of the credentials file [$AKAMAI_EDGERC]
  --section SECTION     Section of the credentials file
                        [$AKAMAI_EDGERC_SECTION]
  --debug               DEBUG mode to generate additional logs for
                        troubleshooting
  --account-key ACCOUNT_KEY
                        Account Switch Key

``` 
## Querying Netstorage NS4

``` 
usage: akamai query [command] netstoragelist [--show-json] [--use-filterstdin]
                                             [--file FILE]
                                             [--template TEMPLATE]
                                             [--edgerc EDGERC]
                                             [--section SECTION] [--debug]
                                             [--account-key ACCOUNT_KEY]

optional arguments:
  --show-json           output json
  --use-filterstdin     use stdin for query
  --file FILE           the json file for query
  --template TEMPLATE   use template name for query
  --edgerc EDGERC       Location of the credentials file [$AKAMAI_EDGERC]
  --section SECTION     Section of the credentials file
                        [$AKAMAI_EDGERC_SECTION]
  --debug               DEBUG mode to generate additional logs for
                        troubleshooting
  --account-key ACCOUNT_KEY
                        Account Switch Key

``` 
## Querying Netstorage Users

``` 
usage: akamai query [command] netstorageuser [--show-json] [--use-filterstdin]
                                             [--file FILE]
                                             [--template TEMPLATE]
                                             [--edgerc EDGERC]
                                             [--section SECTION] [--debug]
                                             [--account-key ACCOUNT_KEY]

optional arguments:
  --show-json           output json
  --use-filterstdin     use stdin for query
  --file FILE           the json file for query
  --template TEMPLATE   use template name for query
  --edgerc EDGERC       Location of the credentials file [$AKAMAI_EDGERC]
  --section SECTION     Section of the credentials file
                        [$AKAMAI_EDGERC_SECTION]
  --debug               DEBUG mode to generate additional logs for
                        troubleshooting
  --account-key ACCOUNT_KEY
                        Account Switch Key

``` 
## Querying Control Center Group CPCodes

``` 
usage: akamai query [command] groupcpcodelist [--show-json]
                                              [--use-filterstdin]
                                              [--file FILE]
                                              [--template TEMPLATE]
                                              [--only-contractIds ONLY_CONTRACTIDS [ONLY_CONTRACTIDS ...]]
                                              [--edgerc EDGERC]
                                              [--section SECTION] [--debug]
                                              [--account-key ACCOUNT_KEY]

optional arguments:
  --show-json           output json
  --use-filterstdin     use stdin for query
  --file FILE           the json file for query
  --template TEMPLATE   use template name for query
  --only-contractIds ONLY_CONTRACTIDS [ONLY_CONTRACTIDS ...]
                        limit the query to specific contracts
  --edgerc EDGERC       Location of the credentials file [$AKAMAI_EDGERC]
  --section SECTION     Section of the credentials file
                        [$AKAMAI_EDGERC_SECTION]
  --debug               DEBUG mode to generate additional logs for
                        troubleshooting
  --account-key ACCOUNT_KEY
                        Account Switch Key

``` 
## Generic Filter Template Utility

``` 
usage: akamai query [command] filtertemplate [--get GET] [--type TYPE]
                                             [--filterfile FILTERFILE]
                                             [--args-use-stdin]
                                             [--arg-list ARG_LIST [ARG_LIST ...]]
                                             [--edgerc EDGERC]
                                             [--section SECTION] [--debug]
                                             [--account-key ACCOUNT_KEY]

optional arguments:
  --get GET             get template details
  --type TYPE           the templates by filter type
  --filterfile FILTERFILE
                        define your own template. Intended to be used with one
                        of the arg list flags
  --args-use-stdin      use stdin as alternative to arg-list param
  --arg-list ARG_LIST [ARG_LIST ...]
                        additional args for a JSONPath condition:
                        #JSONPATHCRITERIA.somekey#
  --edgerc EDGERC       Location of the credentials file [$AKAMAI_EDGERC]
  --section SECTION     Section of the credentials file
                        [$AKAMAI_EDGERC_SECTION]
  --debug               DEBUG mode to generate additional logs for
                        troubleshooting
  --account-key ACCOUNT_KEY
                        Account Switch Key

``` 
## Querying Property Mangager Configurations

``` 
usage: akamai query [command] bulksearch [--show-json] [--use-filterstdin]
                                         [--filterfile FILTERFILE]
                                         [--filtername FILTERNAME]
                                         [--contractId CONTRACTID]
                                         [--network NETWORK]
                                         [--use-searchstdin]
                                         [--searchfile SEARCHFILE]
                                         [--searchname SEARCHNAME]
                                         [--edgerc EDGERC] [--section SECTION]
                                         [--debug] [--account-key ACCOUNT_KEY]

optional arguments:
  --show-json           output json
  --use-filterstdin     get filter json from stdin
  --filterfile FILTERFILE
                        the json file to filter results from bulksearch
  --filtername FILTERNAME
                        template name to filter results from bulksearch
  --contractId CONTRACTID
                        limit the bulk search scope to a specific contract
  --network NETWORK     filter the bulk search result to a specific network
                        (staging or production)
  --use-searchstdin     get bulksearch json from stdin
  --searchfile SEARCHFILE
                        get bulksearch from json file
  --searchname SEARCHNAME
                        get bulksearch by name
  --edgerc EDGERC       Location of the credentials file [$AKAMAI_EDGERC]
  --section SECTION     Section of the credentials file
                        [$AKAMAI_EDGERC_SECTION]
  --debug               DEBUG mode to generate additional logs for
                        troubleshooting
  --account-key ACCOUNT_KEY
                        Account Switch Key

``` 
## Bulk Search Template Utility

``` 
usage: akamai query [command] bulksearchtemplate [--get GET] [--edgerc EDGERC]
                                                 [--section SECTION] [--debug]
                                                 [--account-key ACCOUNT_KEY]

optional arguments:
  --get GET             get template by name
  --edgerc EDGERC       Location of the credentials file [$AKAMAI_EDGERC]
  --section SECTION     Section of the credentials file
                        [$AKAMAI_EDGERC_SECTION]
  --debug               DEBUG mode to generate additional logs for
                        troubleshooting
  --account-key ACCOUNT_KEY
                        Account Switch Key

``` 
### Bulk Search Built In Templates

Out-of-the box bulk searches done on the endpoint. They are listed when running the command:

``` 
akamai query bulksearchtemplate 

[
 "default.json",
 "gtm-origins.json",
 "origins.json",
 "cpcodes.json"
]
 
``` 

default.json bulk search template finds all configuration cpcode values:

``` 
akamai query bulksearchtemplate --get default.json 

{
 "bulkSearchQuery": {
  "syntax": "JSONPATH",
  "match": "$..behaviors[?(@.name == 'cpCode')].options.value.id"
 }
}
 
``` 

origins.json template finds all configuration with their origin values:

``` 
akamai query bulksearchtemplate --get origins.json 

{
 "bulkSearchQuery": {
  "syntax": "JSONPATH",
  "match": "$..behaviors[?(@.name == 'origin')].options.hostname"
 }
}
 
``` 

gtm-origins.json template finds all configurations with gtm origins:

``` 
akamai query bulksearchtemplate --get gtm-origins.json 

{
 "bulkSearchQuery": {
  "syntax": "JSONPATH",
  "match": "$..behaviors[?(@.name == 'origin')].options[?(@.hostname =~ /.*akadns.net$/i)].hostname"
 }
}
 
``` 
