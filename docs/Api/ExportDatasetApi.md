# Swagger\Client\ExportDatasetApi

All URIs are relative to *https://public.opendatasoft.com/api/v2*

Method | HTTP request | Description
------------- | ------------- | -------------
[**exportRecordsCSV**](ExportDatasetApi.md#exportRecordsCSV) | **GET** /{source}/datasets/{dataset_id}/exports/csv | 
[**exportRecordsGEOJSON**](ExportDatasetApi.md#exportRecordsGEOJSON) | **GET** /{source}/datasets/{dataset_id}/exports/geojson | 
[**exportRecordsICAL**](ExportDatasetApi.md#exportRecordsICAL) | **GET** /{source}/datasets/{dataset_id}/exports/ical | 
[**exportRecordsJSON**](ExportDatasetApi.md#exportRecordsJSON) | **GET** /{source}/datasets/{dataset_id}/exports/json | 
[**exportRecordsOV2**](ExportDatasetApi.md#exportRecordsOV2) | **GET** /{source}/datasets/{dataset_id}/exports/ov2 | 
[**exportRecordsSHP**](ExportDatasetApi.md#exportRecordsSHP) | **GET** /{source}/datasets/{dataset_id}/exports/shp | 
[**exportRecordsXLS**](ExportDatasetApi.md#exportRecordsXLS) | **GET** /{source}/datasets/{dataset_id}/exports/xls | 


# **exportRecordsCSV**
> \SplFileObject exportRecordsCSV($source, $dataset_id, $where, $rows, $start, $sort, $select, $timezone, $delimiter)



Export dataset in CSV format

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


$apiInstance = new Swagger\Client\Api\ExportDatasetApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$dataset_id = "dataset_id_example"; // string | Dataset identifier.  Can be found in the \"information\" tab of the dataset page.
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$rows = -1; // int | Number of items to return in export.  Use -1 to retrieve all records
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$sort = array("sort_example"); // string[] | A list of field names, each possibly prefixed with a minus (-).  May also be 'random(seed)', where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields' values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation.
$select = "select_example"; // string | A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard ('*'): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.
$timezone = "UTC"; // string | Set timezone for datetime fields
$delimiter = ";"; // string | Provide a different delimiter (default ',').

try {
    $result = $apiInstance->exportRecordsCSV($source, $dataset_id, $where, $rows, $start, $sort, $select, $timezone, $delimiter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportDatasetApi->exportRecordsCSV: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **dataset_id** | **string**| Dataset identifier.  Can be found in the \&quot;information\&quot; tab of the dataset page. |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **rows** | **int**| Number of items to return in export.  Use -1 to retrieve all records | [optional] [default to -1]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **sort** | [**string[]**](../Model/string.md)| A list of field names, each possibly prefixed with a minus (-).  May also be &#39;random(seed)&#39;, where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields&#39; values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation. | [optional]
 **select** | **string**| A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard (&#39;*&#39;): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with &#39;spa&#39;   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: &#39;size * 2 as bigger_size&#39; will return a new field named bigger_size and containing the double of size field value. | [optional]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]
 **delimiter** | **string**| Provide a different delimiter (default &#39;,&#39;). | [optional] [default to ;]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/csv

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **exportRecordsGEOJSON**
> \SplFileObject exportRecordsGEOJSON($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $timezone, $pretty)



Export dataset in GEOJSON format

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


$apiInstance = new Swagger\Client\Api\ExportDatasetApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$dataset_id = "dataset_id_example"; // string | Dataset identifier.  Can be found in the \"information\" tab of the dataset page.
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = -1; // int | Number of items to return in export.  Use -1 to retrieve all records
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$sort = array("sort_example"); // string[] | A list of field names, each possibly prefixed with a minus (-).  May also be 'random(seed)', where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields' values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation.
$select = "select_example"; // string | A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard ('*'): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.
$timezone = "UTC"; // string | Set timezone for datetime fields
$pretty = false; // bool | Activate pretty print

try {
    $result = $apiInstance->exportRecordsGEOJSON($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $timezone, $pretty);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportDatasetApi->exportRecordsGEOJSON: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **dataset_id** | **string**| Dataset identifier.  Can be found in the \&quot;information\&quot; tab of the dataset page. |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return in export.  Use -1 to retrieve all records | [optional] [default to -1]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **sort** | [**string[]**](../Model/string.md)| A list of field names, each possibly prefixed with a minus (-).  May also be &#39;random(seed)&#39;, where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields&#39; values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation. | [optional]
 **select** | **string**| A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard (&#39;*&#39;): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with &#39;spa&#39;   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: &#39;size * 2 as bigger_size&#39; will return a new field named bigger_size and containing the double of size field value. | [optional]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]
 **pretty** | **bool**| Activate pretty print | [optional] [default to false]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **exportRecordsICAL**
> \SplFileObject exportRecordsICAL($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $timezone)



Export dataset in ICAL format

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


$apiInstance = new Swagger\Client\Api\ExportDatasetApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$dataset_id = "dataset_id_example"; // string | Dataset identifier.  Can be found in the \"information\" tab of the dataset page.
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = -1; // int | Number of items to return in export.  Use -1 to retrieve all records
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$sort = array("sort_example"); // string[] | A list of field names, each possibly prefixed with a minus (-).  May also be 'random(seed)', where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields' values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation.
$select = "select_example"; // string | A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard ('*'): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.
$timezone = "UTC"; // string | Set timezone for datetime fields

try {
    $result = $apiInstance->exportRecordsICAL($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $timezone);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportDatasetApi->exportRecordsICAL: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **dataset_id** | **string**| Dataset identifier.  Can be found in the \&quot;information\&quot; tab of the dataset page. |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return in export.  Use -1 to retrieve all records | [optional] [default to -1]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **sort** | [**string[]**](../Model/string.md)| A list of field names, each possibly prefixed with a minus (-).  May also be &#39;random(seed)&#39;, where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields&#39; values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation. | [optional]
 **select** | **string**| A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard (&#39;*&#39;): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with &#39;spa&#39;   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: &#39;size * 2 as bigger_size&#39; will return a new field named bigger_size and containing the double of size field value. | [optional]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **exportRecordsJSON**
> \SplFileObject exportRecordsJSON($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $pretty, $timezone)



Export dataset in JSON format

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


$apiInstance = new Swagger\Client\Api\ExportDatasetApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$dataset_id = "dataset_id_example"; // string | Dataset identifier.  Can be found in the \"information\" tab of the dataset page.
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = -1; // int | Number of items to return in export.  Use -1 to retrieve all records
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$sort = array("sort_example"); // string[] | A list of field names, each possibly prefixed with a minus (-).  May also be 'random(seed)', where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields' values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation.
$select = "select_example"; // string | A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard ('*'): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.
$pretty = false; // bool | Activate pretty print
$timezone = "UTC"; // string | Set timezone for datetime fields

try {
    $result = $apiInstance->exportRecordsJSON($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $pretty, $timezone);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportDatasetApi->exportRecordsJSON: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **dataset_id** | **string**| Dataset identifier.  Can be found in the \&quot;information\&quot; tab of the dataset page. |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return in export.  Use -1 to retrieve all records | [optional] [default to -1]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **sort** | [**string[]**](../Model/string.md)| A list of field names, each possibly prefixed with a minus (-).  May also be &#39;random(seed)&#39;, where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields&#39; values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation. | [optional]
 **select** | **string**| A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard (&#39;*&#39;): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with &#39;spa&#39;   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: &#39;size * 2 as bigger_size&#39; will return a new field named bigger_size and containing the double of size field value. | [optional]
 **pretty** | **bool**| Activate pretty print | [optional] [default to false]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **exportRecordsOV2**
> \SplFileObject exportRecordsOV2($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $timezone)



Export dataset in OV2 format

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


$apiInstance = new Swagger\Client\Api\ExportDatasetApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$dataset_id = "dataset_id_example"; // string | Dataset identifier.  Can be found in the \"information\" tab of the dataset page.
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = -1; // int | Number of items to return in export.  Use -1 to retrieve all records
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$sort = array("sort_example"); // string[] | A list of field names, each possibly prefixed with a minus (-).  May also be 'random(seed)', where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields' values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation.
$select = "select_example"; // string | A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard ('*'): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.
$timezone = "UTC"; // string | Set timezone for datetime fields

try {
    $result = $apiInstance->exportRecordsOV2($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $timezone);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportDatasetApi->exportRecordsOV2: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **dataset_id** | **string**| Dataset identifier.  Can be found in the \&quot;information\&quot; tab of the dataset page. |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return in export.  Use -1 to retrieve all records | [optional] [default to -1]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **sort** | [**string[]**](../Model/string.md)| A list of field names, each possibly prefixed with a minus (-).  May also be &#39;random(seed)&#39;, where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields&#39; values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation. | [optional]
 **select** | **string**| A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard (&#39;*&#39;): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with &#39;spa&#39;   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: &#39;size * 2 as bigger_size&#39; will return a new field named bigger_size and containing the double of size field value. | [optional]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **exportRecordsSHP**
> \SplFileObject exportRecordsSHP($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $timezone)



Export dataset in Esri shapefile (shp) format

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


$apiInstance = new Swagger\Client\Api\ExportDatasetApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$dataset_id = "dataset_id_example"; // string | Dataset identifier.  Can be found in the \"information\" tab of the dataset page.
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = -1; // int | Number of items to return in export.  Use -1 to retrieve all records
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$sort = array("sort_example"); // string[] | A list of field names, each possibly prefixed with a minus (-).  May also be 'random(seed)', where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields' values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation.
$select = "select_example"; // string | A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard ('*'): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.
$timezone = "UTC"; // string | Set timezone for datetime fields

try {
    $result = $apiInstance->exportRecordsSHP($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $timezone);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportDatasetApi->exportRecordsSHP: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **dataset_id** | **string**| Dataset identifier.  Can be found in the \&quot;information\&quot; tab of the dataset page. |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return in export.  Use -1 to retrieve all records | [optional] [default to -1]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **sort** | [**string[]**](../Model/string.md)| A list of field names, each possibly prefixed with a minus (-).  May also be &#39;random(seed)&#39;, where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields&#39; values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation. | [optional]
 **select** | **string**| A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard (&#39;*&#39;): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with &#39;spa&#39;   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: &#39;size * 2 as bigger_size&#39; will return a new field named bigger_size and containing the double of size field value. | [optional]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/zip

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **exportRecordsXLS**
> \SplFileObject exportRecordsXLS($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $timezone)



Export dataset in XLS (Excel) format

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


$apiInstance = new Swagger\Client\Api\ExportDatasetApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$dataset_id = "dataset_id_example"; // string | Dataset identifier.  Can be found in the \"information\" tab of the dataset page.
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = -1; // int | Number of items to return in export.  Use -1 to retrieve all records
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$sort = array("sort_example"); // string[] | A list of field names, each possibly prefixed with a minus (-).  May also be 'random(seed)', where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields' values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation.
$select = "select_example"; // string | A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard ('*'): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.
$timezone = "UTC"; // string | Set timezone for datetime fields

try {
    $result = $apiInstance->exportRecordsXLS($source, $dataset_id, $where, $search, $rows, $start, $sort, $select, $timezone);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportDatasetApi->exportRecordsXLS: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **dataset_id** | **string**| Dataset identifier.  Can be found in the \&quot;information\&quot; tab of the dataset page. |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return in export.  Use -1 to retrieve all records | [optional] [default to -1]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **sort** | [**string[]**](../Model/string.md)| A list of field names, each possibly prefixed with a minus (-).  May also be &#39;random(seed)&#39;, where seed can be omitted but if specified must be an int. This allows to keep relative ordering during pagination.  Sorts results according to the specified fields&#39; values. By default, the sort is ascending (from the highest value to the smallest value). A minus sign (‘-‘) may be used to perform a descending sort. Sorting is only available on numeric fields (int, double, date and datetime) and on text fields which have the sortable annotation. | [optional]
 **select** | **string**| A select expression can be used to add, remove or change fields to return. An expression can be:   - a wildcard (&#39;*&#39;): return all fields   - a field name: return only this field   - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with &#39;spa&#39;   - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: &#39;size * 2 as bigger_size&#39; will return a new field named bigger_size and containing the double of size field value. | [optional]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: xls

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

