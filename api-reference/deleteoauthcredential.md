+++
title = "DeleteOAuthCredential"
toc = true
+++

Deletes an OAuth Credential Record.

Removes OAuth Credential record. This action cannot be undone.

### Request Parameters

| Parameter | Type | Description | Required |
| --------- | ---- | ----------- | -------- |
| action | string | "DeleteOAuthCredential" | Required |
| credentialId | int | The credential id to be deleted | Required |

### Response Parameters

| Parameter | Type | Description |
| --------- | ---- | ----------- |
| result | string | The result of the operation: success or error |
| credentialId | int | The credential id that was deleted |


### Example Request (CURL)

```
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://www.example.com/includes/api.php');
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS,
    http_build_query(
        array(
            'action' => 'DeleteOAuthCredential',
            'username' => 'ADMIN_USERNAME',
            'password' => 'ADMIN_PASSWORD',
            'credentialId' => '1',
            'responsetype' => 'json',
        )
    )
);
$response = curl_exec($ch);
curl_close($ch);
```


### Example Request (Local API)

```
$command = 'DeleteOAuthCredential';
$postData = array(
    'credentialId' => '1',
);
$adminUsername = 'ADMIN_USERNAME';

$results = localAPI($command, $postData, $adminUsername);
print_r($results);
```


### Example Response JSON

```
{
    "result": "success",
    "credentialId": "1"
}
```


### Error Responses

Possible error condition responses include:

* Invalid Credential ID provided.


### Version History

| Version | Changelog |
| ------- | --------- |
| 1.0 | Initial Version |
