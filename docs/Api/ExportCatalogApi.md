# Swagger\Client\ExportCatalogApi

All URIs are relative to *https://public.opendatasoft.com/api/v2*

Method | HTTP request | Description
------------- | ------------- | -------------
[**exportDatasetsCSV**](ExportCatalogApi.md#exportDatasetsCSV) | **GET** /{source}/exports/csv | 
[**exportDatasetsJson**](ExportCatalogApi.md#exportDatasetsJson) | **GET** /{source}/exports/json | 
[**exportDatasetsRDF**](ExportCatalogApi.md#exportDatasetsRDF) | **GET** /{source}/exports/rdf | 
[**exportDatasetsRSS**](ExportCatalogApi.md#exportDatasetsRSS) | **GET** /{source}/exports/rss | 
[**exportDatasetsTTL**](ExportCatalogApi.md#exportDatasetsTTL) | **GET** /{source}/exports/ttl | 
[**exportDatasetsXLS**](ExportCatalogApi.md#exportDatasetsXLS) | **GET** /{source}/exports/xls | 


# **exportDatasetsCSV**
> \SplFileObject exportDatasetsCSV($source, $where, $search, $rows, $start, $timezone, $include_app_metas, $delimiter)



Export catalog (source) in CSV format

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


$apiInstance = new Swagger\Client\Api\ExportCatalogApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = 10; // int | Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points.
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$timezone = "UTC"; // string | Set timezone for datetime fields
$include_app_metas = false; // bool | Explicitely request application metas for each datasets.
$delimiter = ";"; // string | Provide a different delimiter (default ',').

try {
    $result = $apiInstance->exportDatasetsCSV($source, $where, $search, $rows, $start, $timezone, $include_app_metas, $delimiter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportCatalogApi->exportDatasetsCSV: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points. | [optional] [default to 10]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]
 **include_app_metas** | **bool**| Explicitely request application metas for each datasets. | [optional] [default to false]
 **delimiter** | **string**| Provide a different delimiter (default &#39;,&#39;). | [optional] [default to ;]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/csv

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **exportDatasetsJson**
> \SplFileObject exportDatasetsJson($source, $where, $search, $rows, $start, $pretty, $timezone, $include_app_metas)



Export catalog (source) in JSON format

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


$apiInstance = new Swagger\Client\Api\ExportCatalogApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = 10; // int | Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points.
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$pretty = false; // bool | Activate pretty print
$timezone = "UTC"; // string | Set timezone for datetime fields
$include_app_metas = false; // bool | Explicitely request application metas for each datasets.

try {
    $result = $apiInstance->exportDatasetsJson($source, $where, $search, $rows, $start, $pretty, $timezone, $include_app_metas);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportCatalogApi->exportDatasetsJson: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points. | [optional] [default to 10]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **pretty** | **bool**| Activate pretty print | [optional] [default to false]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]
 **include_app_metas** | **bool**| Explicitely request application metas for each datasets. | [optional] [default to false]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **exportDatasetsRDF**
> \SplFileObject exportDatasetsRDF($source, $where, $search, $rows, $start, $timezone, $include_app_metas)



Export catalog (source) in RDF/XML format

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


$apiInstance = new Swagger\Client\Api\ExportCatalogApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = 10; // int | Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points.
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$timezone = "UTC"; // string | Set timezone for datetime fields
$include_app_metas = false; // bool | Explicitely request application metas for each datasets.

try {
    $result = $apiInstance->exportDatasetsRDF($source, $where, $search, $rows, $start, $timezone, $include_app_metas);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportCatalogApi->exportDatasetsRDF: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points. | [optional] [default to 10]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]
 **include_app_metas** | **bool**| Explicitely request application metas for each datasets. | [optional] [default to false]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/rdf+xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **exportDatasetsRSS**
> \SplFileObject exportDatasetsRSS($source, $where, $search, $rows, $start, $timezone, $include_app_metas)



Export catalog (source) in RSS format

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


$apiInstance = new Swagger\Client\Api\ExportCatalogApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = 10; // int | Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points.
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$timezone = "UTC"; // string | Set timezone for datetime fields
$include_app_metas = false; // bool | Explicitely request application metas for each datasets.

try {
    $result = $apiInstance->exportDatasetsRSS($source, $where, $search, $rows, $start, $timezone, $include_app_metas);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportCatalogApi->exportDatasetsRSS: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points. | [optional] [default to 10]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]
 **include_app_metas** | **bool**| Explicitely request application metas for each datasets. | [optional] [default to false]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **exportDatasetsTTL**
> \SplFileObject exportDatasetsTTL($source, $where, $search, $rows, $start, $timezone, $include_app_metas)



Export catalog (source) in TTL (turtle/rdf) format

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


$apiInstance = new Swagger\Client\Api\ExportCatalogApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = 10; // int | Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points.
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$timezone = "UTC"; // string | Set timezone for datetime fields
$include_app_metas = false; // bool | Explicitely request application metas for each datasets.

try {
    $result = $apiInstance->exportDatasetsTTL($source, $where, $search, $rows, $start, $timezone, $include_app_metas);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportCatalogApi->exportDatasetsTTL: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points. | [optional] [default to 10]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]
 **include_app_metas** | **bool**| Explicitely request application metas for each datasets. | [optional] [default to false]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/turtle

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **exportDatasetsXLS**
> \SplFileObject exportDatasetsXLS($source, $where, $search, $rows, $start, $timezone, $include_app_metas)



Export catalog (source) in XLS (Excel) format

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


$apiInstance = new Swagger\Client\Api\ExportCatalogApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$source = "source_example"; // string | Each source represents a different catalog of datasets you'll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft's repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)
$where = array("where_example"); // string[] | An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.
$search = array("search_example"); // string[] | An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.
$rows = 10; // int | Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points.
$start = 0; // int | Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination.
$timezone = "UTC"; // string | Set timezone for datetime fields
$include_app_metas = false; // bool | Explicitely request application metas for each datasets.

try {
    $result = $apiInstance->exportDatasetsXLS($source, $where, $search, $rows, $start, $timezone, $include_app_metas);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ExportCatalogApi->exportDatasetsXLS: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Each source represents a different catalog of datasets you&#39;ll be able to query.  There are 2 sources available:  * catalog: the catalog of datasets on your portal * opendatasoft: Opendatasoft&#39;s repository of public datasets, also available at   [data.opendatasoft.com](https://data.opendatasoft.com/page/home/) |
 **where** | [**string[]**](../Model/string.md)| An array of filters.  A filter is a text expression performing a simple full-text search that can also include logical operations (NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.  Read [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details. | [optional]
 **search** | [**string[]**](../Model/string.md)| An array of full text search.  A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset. | [optional]
 **rows** | **int**| Number of items to return.  To use in conjonction with start to implement pagination.  Rows maximum value is 100. To retrive more data use export entry points. | [optional] [default to 10]
 **start** | **int**| Index of the first item to return (starting at 0).  To use in conjonction with rows to implement pagination. | [optional] [default to 0]
 **timezone** | **string**| Set timezone for datetime fields | [optional] [default to UTC]
 **include_app_metas** | **bool**| Explicitely request application metas for each datasets. | [optional] [default to false]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[api_key](../../README.md#api_key), [basic](../../README.md#basic)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: xls

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

