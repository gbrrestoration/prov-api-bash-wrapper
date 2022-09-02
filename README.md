# FastAPI Bash client

## Overview

This is a Bash client script for accessing FastAPI service.

The script uses cURL underneath for making all REST calls.

## Usage

```shell
# Make sure the script has executable rights
$ chmod u+x prov-api.sh

# Print the list of operations available on the service
$ ./prov-api.sh -h

# Print the service description
$ ./prov-api.sh --about

# Print detailed information about specific operation
$ ./prov-api.sh <operationId> -h

# Make GET request
./prov-api.sh --host http://<hostname>:<port> --accept xml <operationId> <queryParam1>=<value1> <header_key1>:<header_value2>

# Make GET request using arbitrary curl options (must be passed before <operationId>) to an SSL service using username:password
prov-api.sh -k -sS --tlsv1.2 --host https://<hostname> -u <user>:<password> --accept xml <operationId> <queryParam1>=<value1> <header_key1>:<header_value2>

# Make POST request
$ echo '<body_content>' | prov-api.sh --host <hostname> --content-type json <operationId> -

# Make POST request with simple JSON content, e.g.:
# {
#   "key1": "value1",
#   "key2": "value2",
#   "key3": 23
# }
$ echo '<body_content>' | prov-api.sh --host <hostname> --content-type json <operationId> key1==value1 key2=value2 key3:=23 -

# Make POST request with form data
$ prov-api.sh --host <hostname> <operationId> key1:=value1 key2:=value2 key3:=23

# Preview the cURL command without actually executing it
$ prov-api.sh --host http://<hostname>:<port> --dry-run <operationid>

```

## Docker image

You can easily create a Docker image containing a preconfigured environment
for using the REST Bash client including working autocompletion and short
welcome message with basic instructions, using the generated Dockerfile:

```shell
docker build -t my-rest-client .
docker run -it my-rest-client
```

By default you will be logged into a Zsh environment which has much more
advanced auto completion, but you can switch to Bash, where basic autocompletion
is also available.

## Shell completion

### Bash

The generated bash-completion script can be either directly loaded to the current Bash session using:

```shell
source prov-api.sh.bash-completion
```

Alternatively, the script can be copied to the `/etc/bash-completion.d` (or on OSX with Homebrew to `/usr/local/etc/bash-completion.d`):

```shell
sudo cp prov-api.sh.bash-completion /etc/bash-completion.d/prov-api.sh
```

#### OS X

On OSX you might need to install bash-completion using Homebrew:

```shell
brew install bash-completion
```

and add the following to the `~/.bashrc`:

```shell
if [ -f $(brew --prefix)/etc/bash_completion ]; then
  . $(brew --prefix)/etc/bash_completion
fi
```

### Zsh

In Zsh, the generated `_prov-api.sh` Zsh completion file must be copied to one of the folders under `$FPATH` variable.

## Documentation for API Endpoints

All URIs are relative to **

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccessCheckApi* | [**checkAdminAccess**](docs/AccessCheckApi.md#checkadminaccess) | **GET** /check-access/check-admin-access | Check Admin Access
*AccessCheckApi* | [**checkGeneralAccess**](docs/AccessCheckApi.md#checkgeneralaccess) | **GET** /check-access/check-general-access | Check General Access
*AccessCheckApi* | [**checkReadAccess**](docs/AccessCheckApi.md#checkreadaccess) | **GET** /check-access/check-read-access | Check Read Access
*AccessCheckApi* | [**checkWriteAccess**](docs/AccessCheckApi.md#checkwriteaccess) | **GET** /check-access/check-write-access | Check Write Access
*DefaultApi* | [**root**](docs/DefaultApi.md#root) | **GET** / | Root
*ExploreLineageApi* | [**exploreDownstream**](docs/ExploreLineageApi.md#exploredownstream) | **GET** /explore/downstream | Explore Downstream
*ExploreLineageApi* | [**exploreUpstream**](docs/ExploreLineageApi.md#exploreupstream) | **GET** /explore/upstream | Explore Upstream
*ModelRunsApi* | [**registerCompleteModelRun**](docs/ModelRunsApi.md#registercompletemodelrun) | **POST** /model_run/register_complete | Register Model Run Complete


## Documentation For Models

 - [AssociationInfo](docs/AssociationInfo.md)
 - [DataStoreDatasetResource](docs/DataStoreDatasetResource.md)
 - [Dataset](docs/Dataset.md)
 - [DatasetType](docs/DatasetType.md)
 - [FileSystemResource](docs/FileSystemResource.md)
 - [HTTPValidationError](docs/HTTPValidationError.md)
 - [InputInfo](docs/InputInfo.md)
 - [LineageResponse](docs/LineageResponse.md)
 - [LocationInner](docs/LocationInner.md)
 - [ModelRunRecord](docs/ModelRunRecord.md)
 - [ModelRunWorkflowDefinitionResource](docs/ModelRunWorkflowDefinitionResource.md)
 - [ModellerResource](docs/ModellerResource.md)
 - [OrganisationResource](docs/OrganisationResource.md)
 - [OutputInfo](docs/OutputInfo.md)
 - [ProvenanceRecordInfo](docs/ProvenanceRecordInfo.md)
 - [RegisterModelRunResponse](docs/RegisterModelRunResponse.md)
 - [Status](docs/Status.md)
 - [TemplateResource](docs/TemplateResource.md)
 - [TemplatedDataset](docs/TemplatedDataset.md)
 - [URLDatasetResource](docs/URLDatasetResource.md)
 - [User](docs/User.md)
 - [ValidationError](docs/ValidationError.md)


## Documentation For Authorization


## OAuth2PasswordBearer


- **Type**: OAuth
- **Flow**: password
- **Token URL**: token
- **Scopes**: N/A

