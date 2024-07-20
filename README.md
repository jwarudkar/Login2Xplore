# Login2Xplore

# Student Enrollment Form

The Student Enrollment Form project utilizes JsonPowerDB to manage student registration information efficiently. It provides functionalities for both adding new students and updating existing records based on their Roll No. The form is designed to ensure seamless data entry and validation, enhancing user experience through dynamic interaction.

## Benefits of using JsonPowerDB

- Versatile Data Storage: Supports structured, semi-structured, and unstructured data, accommodating various formats and types.
- Dynamic Relational Management: Allows CRUD operations with relational integrity without the need for predefined schemas like PK, FK, UK.
- Ease of Integration: Utilizes HTTP REST APIs for seamless integration with any technology stack, simplifying development and reducing time-to-market.
- Cost-Effective and Efficient: Lowers development costs by reducing the need for complex infrastructure and accelerating development cycles.

# Release History

## JsonPowerDB

### Version: 1.0

#### Execute API

var baseUrl = "http://api.login2explore.com:5577";
function executeCommand(reqString, apiEndPointUrl) {
var url = baseUrl + apiEndPointUrl;
var jsonObj;
$.post(url, reqString, function (result) {
jsonObj = JSON.parse(result);
}).fail(function (result) {
var dataJsonObj = result.responseText;
jsonObj = JSON.parse(dataJsonObj);
});
return jsonObj;
}

## Create a PUT Request String

function createPUTRequest(connToken, jsonObj, dbName, relName) {
var putRequest = "{\n" + "\"token\" : \"" + connToken + "\"," + "\"dbName\": \"" + dbName + "\",\n" + "\"cmd\" : \"PUT\",\n" + "\"rel\" : \"" + relName + "\"," + "\"jsonStr\": \n" + jsonObj + "\n" + "}";
return putRequest;
}
