# Swagger\Client\CatalogApi

All URIs are relative to *https://public.opendatasoft.com/api/v2*

Method | HTTP request | Description
------------- | ------------- | -------------
[**aggregateDatasets**](CatalogApi.md#aggregateDatasets) | **GET** /{source}/aggregates | 
[**getDatasets**](CatalogApi.md#getDatasets) | **GET** /{source}/datasets | 
[**getDatasetsFacets**](CatalogApi.md#getDatasetsFacets) | **GET** /{source}/facets | 
[**getSource**](CatalogApi.md#getSource) | **GET** /{source} | 


# **aggregateDatasets**
> \Swagger\Client\Model\InlineResponse200 aggregateDatasets($source, $select, $group_by, $where)



Compute aggregations from catalog and return a list of each aggregate indexed by their names.

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


$apiInstance = new Swagger\Client\Api\CatalogApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$select = "select_example"; // string | A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard ('*'): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.
$group_by = "group_by_example"; // string | A group by expression defines a grouping function for an aggregation. It can be:  - a field name: group result by each value of this field  - a range function: group result by range  - a date function: group result by date It is possible to specify a custom name with the 'as name' notation. For instance: group_by='city_field as city'.
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

try {
    $result = $apiInstance->aggregateDatasets($source, $select, $group_by, $where);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CatalogApi->aggregateDatasets: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **select** | **string**| A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard (&#39;*&#39;): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with &#39;spa&#39;   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: &#39;size * 2 as bigger_size&#39; will return a new field named bigger_size and containing the double of size field value. | [optional]
 **group_by** | **string**| A group by expression defines a grouping function for an aggregation. It can be:  - a field name: group result by each value of this field  - a range function: group result by range  - a date function: group result by date It is possible to specify a custom name with the &#39;as name&#39; notation. For instance: group_by&#x3D;&#39;city_field as city&#39;. | [optional]
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]

### Return type

[**\Swagger\Client\Model\InlineResponse200**](../Model/InlineResponse200.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getDatasets**
> object getDatasets($source, $where, $search, $refine, $exclude, $rows, $start, $sort, $pretty, $timezone, $include_app_metas)



List of available datasets, each with their endpoints, paginated.  Links provided: * previous page * next page * last page * first page

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


$apiInstance = new Swagger\Client\Api\CatalogApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$refine = array("refine_example"); // string[] | An array of filter on **facet** value.  This request will be refined on the defined facet value. Refining with a facet is equivalent to selecting an entry in the left navigation panel.  For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details.
$exclude = array("exclude_example"); // string[] | An array of filter on **facet** value.  This request will exclude the defined facet value. For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details.
$rows = 10; // int | Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points.
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$sort = array("sort_example"); // string[] | A list of field names, each possibly prefixed with a minus (-).  May also be 'random(seed)', where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields' values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation.
$pretty = false; // bool | Activate pretty print
$timezone = "UTC"; // string | Set timezone for datetime fields
$include_app_metas = false; // bool | Explicitely request application metas for each datasets.

try {
    $result = $apiInstance->getDatasets($source, $where, $search, $refine, $exclude, $rows, $start, $sort, $pretty, $timezone, $include_app_metas);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CatalogApi->getDatasets: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **refine** | [**string[]**](../Model/string.md)| An array of filter on **facet** value.  This request will be refined on the defined facet value. Refining with a facet is equivalent to selecting an entry in the left navigation panel.  For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details. | [optional]
 **exclude** | [**string[]**](../Model/string.md)| An array of filter on **facet** value.  This request will exclude the defined facet value. For example city:Paris or modified:2019/12  Read [filtering with facets value](https://help.opendatasoft.com/apis/ods-search-v2/#filtering-with-facets-values) for more details. | [optional]
 **rows** | **int**| Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points. | [optional] [default to 10]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **sort** | [**string[]**](../Model/string.md)| A list of field names, each possibly prefixed with a minus (-).  May also be &#39;random(seed)&#39;, where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields&#39; values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation. | [optional]
 **pretty** | **bool**| Activate pretty print | [optional] [default to false]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]
 **include_app_metas** | **bool**| Explicitely request application metas for each datasets. | [optional] [default to false]

### Return type

**object**

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

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


$apiInstance = new Swagger\Client\Api\CatalogApi(
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
    echo 'Exception when calling CatalogApi->getDatasetsFacets: ', $e->getMessage(), PHP_EOL;
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

# **getSource**
> object getSource($source)



Source entry points  Provides links for the source's datasets and metadata.

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


$apiInstance = new Swagger\Client\Api\CatalogApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

try {
    $result = $apiInstance->getSource($source);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CatalogApi->getSource: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |

### Return type

**object**

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

