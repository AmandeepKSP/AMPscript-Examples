### Task   Generate Access Token Via SSJS

```javascript
<script runat="server" language="JavaScript" executioncontexttype="Server" executioncontextname="Access_token_generator">
    Platform.Load("Core", "1");

    var auth_url = "xxxx";  //Repalce with you auth auth_url
    var endpoint = "v2/token";
    var full_url = auth_url + endpoint;

    var payload = {
        "grant_type": "client_credentials",
        "client_id": "xxxxxx",   //Replace with you client_id
        "client_secret": "xxxxx"  //Replace with you client_secret
    };
    var json_body = Platform.Function.Stringify(payload);
    // Use Platform.Function.Http.Post for the HTTP request
    var result = HTTP.Post(full_url, "application/json", json_body);   // it will return an obejct
    if (result.StatusCode == 200) {  
            var responseJson = Platform.Function.ParseJSON(result.Response[0]);  // convert respone in json
            var accessToken = responseJson.access_token; // pick access token form json
            var restUrl = responseJson.rest_instance_url; // pick rest_instance_url form json
      
    } else {
        throw new Error("Error fetching access token. Status code: " + result.StatusCode);
    }

    Write(result.Response[0]); //payload response
    Write("<br>");
    Write("<br>");
    Write("<br>");
  
    Write("Rest API is " +restUrl+ "<br>"); //rest url
    Write("<br>");
    Write("<br>");
    Write("<br>");
    Write(accessToken); //token
</script>
```