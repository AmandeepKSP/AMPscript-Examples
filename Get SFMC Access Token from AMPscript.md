### Task   Generate Access Token Via Ampscript

```ampscript
%%[
VAR  @grant_type, @client_id, @client_secret, @auth_url, @endpoint, @full_url, @payload
VAR  @JSON1, @JSON2, @JSON3, @request, @api_response, @rows, @rowCount, @row, @access_token

/* Define authentication parameters */
SET @grant_type = "client_credentials"
SET @client_id = "xxxxxxxx" /*Replace with you client_id*/
SET @client_secret = "xxxxx"/*Replace with you client_secret*/
SET @auth_url = "xxxxxx" /* Repalce with you auth auth_url*/
SET @endpoint = "v2/token"
SET @full_url = CONCAT(@auth_url, @endpoint)

/* Create the JSON payload */
SET @JSON1 = CONCAT('"grant_type": "', @grant_type, '"')
SET @JSON2 = CONCAT('"client_id": "', @client_id, '"')
SET @JSON3 = CONCAT('"client_secret": "', @client_secret, '"')
SET @payload = CONCAT("{", @JSON1, ",", @JSON2, ",", @JSON3, "}")

/* Make the HTTP POST request */
SET @request = HTTPPost(@full_url, "application/json", @payload, @api_response)

/* Check if the request was successful */
IF @request == "200" THEN

    /* Split the JSON response into rows using a delimiter */
    SET @rows = BuildRowsetFromString(@api_response, '"')

    /* Count the number of rows */
    SET @rowCount = RowCount(@rows)

    /* If rows exist, extract the access token */
    IF @rowCount > 0 THEN

        /* Assuming the access token is in the 4th row, but check the structure */
        SET @row = Row(@rows, 4)
        SET @access_token = Field(@row, 1)

    ELSE
        /* Handle case where no rows were returned */
        SET @access_token = "No data found"
    ENDIF

ELSE
    /* Handle HTTP request failure */
    SET @access_token = "Error: " & @api_response
ENDIF
]%%

<br><br>
API Request Status - %%=v(@request)=%% <br><br>
API Response - %%=v(@api_response)=%% <br><br>
Access Token - %%=v(@access_token)=%% <br><br>
Row Count - %%=v(@rowCount)=%% <br><br>
```

