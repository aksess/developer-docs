+++
title = "AcceptQuote"
toc = true
+++

Accepts a quote

### Request Parameters

| Parameter | Type | Description | Required |
| --------- | ---- | ----------- | -------- |
| action | string | "AcceptQuote" | Required |
| quoteid | int | The quote id to be accepted and converted to an invoice | Required |

### Response Parameters

| Parameter | Type | Description |
| --------- | ---- | ----------- |
| result | string | The result of the operation: success or error |
| invoiceid | int | The newly created invoice id |


### Example Request (CURL)

```
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://www.example.com/includes/api.php');
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS,
    http_build_query(
        array(
            'action' => 'AcceptQuote',
            'username' => 'ADMIN_USERNAME',
            'password' => 'ADMIN_PASSWORD',
            'quoteid' => '1',
            'responsetype' => 'json',
        )
    )
);
$response = curl_exec($ch);
curl_close($ch);
```


### Example Request (Local API)

```
$command = 'AcceptQuote';
$postData = array(
    'quoteid' => '1',
);
$adminUsername = 'ADMIN_USERNAME';

$results = localAPI($command, $postData, $adminUsername);
print_r($results);
```


### Example Response JSON

```
{
    "result": "success"
}
```


### Error Responses

Possible error condition responses include:

* Quote ID Not Found


### Version History

| Version | Changelog |
| ------- | --------- |
| 1.0 | Initial Version |