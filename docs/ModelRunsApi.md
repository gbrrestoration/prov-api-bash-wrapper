# ModelRunsApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**registerCompleteModelRun**](ModelRunsApi.md#registerCompleteModelRun) | **POST** /model_run/register_complete | Register Model Run Complete



## registerCompleteModelRun

Register Model Run Complete

register_model_run_complete
Given the model run record object (schema/model) will:
- validate the ids provided in the model 
    - Validate and retrieve the workflow definition
    - Validate the templates for the input and output datasets 
    - Validate that the provided datasets satisfy all templates
    - Validate that datasets provided through data store exist
- mint a model run record in the registry 
- produce a prov-o document reflecting the input model run record
- update the model run record in the registry with the prov serialisation
  and other information 
- lodge the model run record into the graph database store
- update the record to lodged status 
- return information including the handle id from the model run record

Arguments
----------
record : ModelRunRecord
    The model run record to lodge into the graph store and registry

Returns
-------
 : RegisterModelRunResponse
    The response including the handle id and record information

Raises
------
HTTPException
    If something goes wrong when validating the IDs returns a 400 error.

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
prov-api.sh registerCompleteModelRun
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **modelRunRecord** | [**ModelRunRecord**](ModelRunRecord.md) |  |

### Return type

[**RegisterModelRunResponse**](RegisterModelRunResponse.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

