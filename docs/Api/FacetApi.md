# Swagger\Client\FacetApi

All URIs are relative to *https://public.opendatasoft.com/api/v2*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getDatasetsFacets**](FacetApi.md#getDatasetsFacets) | **GET** /{source}/facets | 
[**getRecordsFacets**](FacetApi.md#getRecordsFacets) | **GET** /{source}/datasets/{dataset_id}/facets | 


# **getDatasetsFacets**
> \Swagger\Client\Model\InlineResponse2001 getDatasetsFacets($source, $facet, $refine, $exclude, $where, $search, $timezone)



Enumerate facets values for datasets and return a list of values for each facet. Can be used to implement guided navigation in large result sets.  Read [the facets documentation](https://help.opendatasoft.com/apis/ods-search-v2/#enumerating-facets-values) for more details.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: api_key
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKey('apikey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apikey', 'Bearer');
// Configure HTTP basic authorization: basic
$config = Swagger\Client\Configuration::getDefaultConfiguration()
              ->setUsername('YOUR_USERNAME')
              ->setPassword('YOUR_PASSWORD');


$apiInstance = new Swagger\Client\Api\FacetApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$facet = array("facet_example"); // string[] | An array of facets names  A facet is a field used for filtering and exploration. To use a field as a facet, you have to configure it in your back office.  Read [the facets documentation](https://help.opendatasoft.com/apis/ods-search-v2/#facets) for more details.
$refine = array("refine_example"); // string[] | An array of filter on **facet** value.  This request will be refined on the defined facet value. Refining with a facet is equivalent to selecting an entry in the left navigation panel.  For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details.
$exclude = array("exclude_example"); // string[] | An array of filter on **facet** value.  This request will exclude the defined facet value. For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details.
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$timezone = "UTC"; // string | Set timezone for datetime fields

try {
    $result = $apiInstance->getDatasetsFacets($source, $facet, $refine, $exclude, $where, $search, $timezone);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FacetApi->getDatasetsFacets: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **facet** | [**string[]**](../Model/string.md)| An array of facets names  A facet is a field used for filtering and exploration. To use a field as a facet, you have to configure it in your back office.  Read [the facets documentation](https://help.opendatasoft.com/apis/ods-search-v2/#facets) for more details. | [optional]
 **refine** | [**string[]**](../Model/string.md)| An array of filter on **facet** value.  This request will be refined on the defined facet value. Refining with a facet is equivalent to selecting an entry in the left navigation panel.  For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details. | [optional]
 **exclude** | [**string[]**](../Model/string.md)| An array of filter on **facet** value.  This request will exclude the defined facet value. For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details. | [optional]
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]

### Return type

[**\Swagger\Client\Model\InlineResponse2001**](../Model/InlineResponse2001.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getRecordsFacets**
> \Swagger\Client\Model\InlineResponse2001 getRecordsFacets($source, $dataset_id, $facet, $refine, $exclude, $where, $search, $timezone)



Enumerate facets values for records and return a list of values for each facet. Can be used to implement guided navigation in large result sets.  Read [the facets documentation](https://help.opendatasoft.com/apis/ods-search-v2/#enumerating-facets-values) for more details.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: api_key
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKey('apikey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apikey', 'Bearer');
// Configure HTTP basic authorization: basic
$config = Swagger\Client\Configuration::getDefaultConfiguration()
              ->setUsername('YOUR_USERNAME')
              ->setPassword('YOUR_PASSWORD');


$apiInstance = new Swagger\Client\Api\FacetApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$dataset_id = "dataset_id_example"; // string | Dataset identifier.  Can be found in the \"information\" tab of the dataset page.
$facet = array("facet_example"); // string[] | An array of facets names  A facet is a field used for filtering and exploration. To use a field as a facet, you have to configure it in your back office.  Read [the facets documentation](https://help.opendatasoft.com/apis/ods-search-v2/#facets) for more details.
$refine = array("refine_example"); // string[] | An array of filter on **facet** value.  This request will be refined on the defined facet value. Refining with a facet is equivalent to selecting an entry in the left navigation panel.  For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details.
$exclude = array("exclude_example"); // string[] | An array of filter on **facet** value.  This request will exclude the defined facet value. For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details.
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$timezone = "UTC"; // string | Set timezone for datetime fields

try {
    $result = $apiInstance->getRecordsFacets($source, $dataset_id, $facet, $refine, $exclude, $where, $search, $timezone);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FacetApi->getRecordsFacets: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **dataset_id** | **string**| Dataset identifier.  Can be found in the \&quot;information\&quot; tab of the dataset page. |
 **facet** | [**string[]**](../Model/string.md)| An array of facets names  A facet is a field used for filtering and exploration. To use a field as a facet, you have to configure it in your back office.  Read [the facets documentation](https://help.opendatasoft.com/apis/ods-search-v2/#facets) for more details. | [optional]
 **refine** | [**string[]**](../Model/string.md)| An array of filter on **facet** value.  This request will be refined on the defined facet value. Refining with a facet is equivalent to selecting an entry in the left navigation panel.  For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details. | [optional]
 **exclude** | [**string[]**](../Model/string.md)| An array of filter on **facet** value.  This request will exclude the defined facet value. For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details. | [optional]
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]

### Return type

[**\Swagger\Client\Model\InlineResponse2001**](../Model/InlineResponse2001.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

