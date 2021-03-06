+++
title = "DomainGetWhoisInfo"
toc = true
+++

Obtains the current whois information for the domain.

Connects to the registrar and obtains the whois information for the domain

### Request Parameters

| Parameter | Type | Description | Required |
| --------- | ---- | ----------- | -------- |
| action | string | "DomainGetWhoisInfo" | Required |
| domainid | int | The id of the domain to obtain the whois information for | Required |

### Response Parameters

| Parameter | Type | Description |
| --------- | ---- | ----------- |
| result | string | The result of the operation: success or error |
| Registrant | array | The registrant contact details |
| Admin | array | The admin contact details |
| Tech | array | The registrant contact details |


### Example Request (CURL)

```
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://www.example.com/includes/api.php');
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS,
    http_build_query(
        array(
            'action' => 'DomainGetWhoisInfo',
            'username' => 'ADMIN_USERNAME',
            'password' => 'ADMIN_PASSWORD',
            'domainid' => '1',
            'responsetype' => 'json',
        )
    )
);
$response = curl_exec($ch);
curl_close($ch);
```


### Example Request (Local API)

```
$command = 'DomainGetWhoisInfo';
$postData = array(
    'domainid' => '1',
);
$adminUsername = 'ADMIN_USERNAME';

$results = localAPI($command, $postData, $adminUsername);
print_r($results);
```


### Example Response JSON

```
{
    "result": "success",
    "Registrant": "{\"First_Name\":\"Test\",\"Last_Name\":\"Client\",\"Organisation_Name\":null,\"Job_Title\":null,\"Email\":\"test@testemail.com\",\"Address_1\":\"123 Test Street\",\"Address_2\":\"\",\"City\":\"Test\",\"State\":\"Test\",\"Postcode\":\"TE5 5ST\",\"Country\":GB,\"Phone\":\"+44.1234567890\"}"
}
```


### Error Responses

Possible error condition responses include:

* Domain ID Not Found
* Registrar Error Message


### Version History

| Version | Changelog |
| ------- | --------- |
| 1.0 | Initial Version |
