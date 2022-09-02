# ExploreLineageApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**exploreDownstream**](ExploreLineageApi.md#exploreDownstream) | **GET** /explore/downstream | Explore Downstream
[**exploreUpstream**](ExploreLineageApi.md#exploreUpstream) | **GET** /explore/upstream | Explore Upstream



## exploreDownstream

Explore Downstream

explore_downstream
Explores in the downstream direction (outputs/results)
starting at the specified node handle ID. The search 
depth is bounded by the depth parameter which has a default
maximum of 100.

Arguments
----------
starting_id : str
    The handle ID to start at.
depth : int, optional
    The maximum depth to traverse in this direction, by default DEPTH_UPPER_LIMIT

Returns
-------
 : LineageResponse
    A status, node count, and networkx serialised graph response.

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
prov-api.sh exploreDownstream  starting_id=value  depth=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **startingId** | **string** |  | [default to null]
 **depth** | **integer** |  | [optional] [default to null]

### Return type

[**LineageResponse**](LineageResponse.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## exploreUpstream

Explore Upstream

explore_upstream
Explores in the upstream direction (inputs/associations)
starting at the specified node handle ID. The search 
depth is bounded by the depth parameter which has a default
maximum of 100.

Arguments
----------
starting_id : str
    The handle ID to start at.
depth : int, optional
    The maximum depth to traverse in this direction, by default DEPTH_UPPER_LIMIT

Returns
-------
 : LineageResponse
    A status, node count, and networkx serialised graph response.

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
prov-api.sh exploreUpstream  starting_id=value  depth=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **startingId** | **string** |  | [default to null]
 **depth** | **integer** |  | [optional] [default to null]

### Return type

[**LineageResponse**](LineageResponse.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

