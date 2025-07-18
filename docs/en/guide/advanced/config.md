# Configuration items

## Complete configuration

|                                 Configuration                                  | Version | Required | Type           |       Default       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|:------------------------------------------------------------------------------:|:-------:|:--------:|----------------|:-------------------:|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                   `outPath`                                    |         |    ✔     | `String`       |                     | Specify the output path of the document                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                  `serverUrl`                                   |         |    ❌     | `String`       | `http://127.0.0.1`  | Server address, when exporting `postman` it is recommended to set it to `http://{{server}}` for convenience and directly in `postman` Set environment variables. It is recommended to use `serverEnv` when exporting `postman` after `2.4.8` to avoid modifying the configuration during multiple exports.                                                                                                                                                                                                                   |
|                                  `serverEnv`                                   | `2.4.8` |    ❌     | `String`       |                     | Server address, when exporting `postman` it is recommended to set it to `http://{{server}}` to facilitate setting environment variables directly in `postman`. The configuration is changed to support postman export without globally modifying `serverUrl`                                                                                                                                                                                                                                                                 |
|                                  `pathPrefix`                                  | `2.2.3` |    ❌     | `String`       |                     | Set the `path` prefix, such as configuring `Servlet ContextPath`.                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|                                   `isStrict`                                   |         |    ❌     | `Boolean`      |                     | Whether to enable strict mode. Strict mode will force code comments to be checked. When setting this item in `2.6.3` or later plug-in versions, if annotation errors are detected, the plug-in will be directly interrupted. White nested build cycles. For team use, it is recommended to set it to `true` to increase the annotation requirements for developers and improve the completeness of the documentation.                                                                                                        |
|                                   `allInOne`                                   |         |    ❌     | `Boolean`      |       `false`       | Whether to merge documents into one file, `true` is generally recommended.                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|                                   `coverOld`                                   |         |    ❌     | `Boolean`      |       `false`       | Whether to overwrite old files, mainly used for `Markdown` file coverage.                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|                               `createDebugPage`                                | `2.0.1` |    ❌     | `Boolean`      |       `false`       | `smart-doc` supports creating an `HTML` document page with a debuggable interface similar to `Swagger`, only in `AllInOne` function in the mode. Starting from @2.0.1, for HTML documents, debug pages can be generated in both allInOne and non-allInOne modes.                                                                                                                                                                                                                                                             |
|                      [`packageFilters`](#packagefilters)                       |         |    ❌     | `String`       |                     | `Controller` package filtering, multiple packages separated by English commas. <br />`2.2.2` starts to use regular rules: `com.test.controller.*` <br />`2.7.1` starts to support method level regular rules: `com.test.controller.TestController.*`                                                                                                                                                                                                                                                                         |
|                            `packageExcludeFilters`                             |         |    ❌     | `String`       |                     | Exclude subpackages for `packageFilters`, multiple packages are separated by English commas<br />Since `2.2.2`, regular rules must be used: `com.test.controller. res.*`                                                                                                                                                                                                                                                                                                                                                     |
|                             `md5EncryptedHtmlName`                             |         |    ❌     | `Boolean`      |       `false`       | Used only if each `Controller` generates an `HTML` file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|                                    `style`                                     |         |    ❌     | `String`       |                     | [Code Highlight](https://highlightjs.org/) settings based on `highlight.js`.                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                 `projectName`                                  |         |    ❌     | `String`       |                     | Used only if each `Controller` generates an `HTML` file. If `projectName` is not set in `smart-doc.json` or in the plugin, starting from `2.3.4`, the plugin automatically uses the `projectName` in `pom` as the default filling, so it does not need to be configured when using the plugin.                                                                                                                                                                                                                               |
|                              `skipTransientField`                              | `1.7.8` |    ❌     | `Boolean`      |       `true`        | Deprecated since 3.0.8. Use `serializeRequestTransients` and`serializeResponseTransients` instead. This configuration was used to skip the serialization of transient fields in request and response bodies.                                                                                                                                                                                                                                                                                                                 |
|                          `serializeRequestTransients`                          | `3.0.8` |    ❌     | `Boolean`      |       `false`       | Determines whether transient fields in request objects should be serialized. When set to `true`, transient fields will be included in the request serialization.                                                                                                                                                                                                                                                                                                                                                             |
|                         `serializeResponseTransients`                          | `3.0.8` |    ❌     | `Boolean`      |       `false`       | Determines whether transient fields in response objects should be serialized. When set to`true`, transient fields will be included in the response serialization.                                                                                                                                                                                                                                                                                                                                                            |
|                                 `sortByTitle`                                  | `1.8.7` |    ❌     | `Boolean`      |       `false`       | Interface sorting by title.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|                                  `showAuthor`                                  |         |    ❌     | `Boolean`      |       `true`        | Whether to display the interface author name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|                           `requestFieldToUnderline`                            | `1.8.7` |    ❌     | `Boolean`      |       `false`       | Automatically convert camel case input fields to underline format in the document.                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|                           `responseFieldToUnderline`                           | `1.8.7` |    ❌     | `Boolean`      |       `false`       | Automatically convert camelCase response fields to underline format in the document.                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|                                  `inlineEnum`                                  | `1.8.8` |    ❌     | `Boolean`      |       `false`       | Whether to display the enumeration details in the parameter table.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|                                `recursionLimit`                                | `1.8.8` |    ❌     | `int`          |         `7`         | Set the number of recursive executions allowed to avoid some object parsing problems.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                             `allInOneDocFileName`                              | `1.9.0` |    ❌     | `String`       |    `index.html`     | It only takes effect when all `Controller` of the project are configured to generate an `HTML` file.                                                                                                                                                                                                                                                                                                                                                                                                                         |
|                                `requestExample`                                | `1.9.0` |    ❌     | `Boolean`      |       `true`        | Whether to display request examples in the documentation.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|                               `responseExample`                                | `1.9.0` |    ❌     | `Boolean`      |       `true`        | Whether to display response examples in the documentation.                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|                                  `urlSuffix`                                   | `2.1.0` |    ❌     | `String`       |                     | Support `url` suffix of `SpringMVC` old project.                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                                   `language`                                   |         |    ❌     | `String`       |      `CHINESE`      | Internationalization support for mock values.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|                              `displayActualType`                               | `1.9.6` |    ❌     | `Boolean`      |       `false`       | Whether to automatically display the short class name of the generic real type in the comment column.                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                                    `appKey`                                    | `2.0.9` |    ❌     | `String`       |                     | `torna` platform connects to `appKey`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|                                   `appToken`                                   | `2.0.9` |    ❌     | `String`       |                     | `torna` platform `appToken`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                    `secret`                                    | `2.0.9` |    ❌     | `String`       |                     | `torna` platform `secret`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|                                   `openUrl`                                    | `2.0.9` |    ❌     | `String`       |                     | `torna` platform address, fill in your own private deployment address.                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|                                 `debugEnvName`                                 |         |    ❌     | `String`       |                     | `torna` environment name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|                                   `replace`                                    | `2.2.4` |    ❌     | `Boolean`      |       `true`        | Replace old documents when pushing `torna`. Changes will still be pushed to the past and covered. This function is mainly to ensure that the code is deleted and not deleted on `torna`.                                                                                                                                                                                                                                                                                                                                     |
|                                 `debugEnvUrl`                                  | `2.0.9` |    ❌     | `String`       |                     | Push `torna` configuration interface service address.                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                                  `tornaDebug`                                  | `2.0.9` |    ❌     | `Boolean`      |       `true`        | Whether to print `torna` push log.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|                             `ignoreRequestParams`                              | `1.9.2` |    ❌     | `List<String>` |                     | Ignore request parameter objects and block parameter objects that do not want to generate documents.                                                                                                                                                                                                                                                                                                                                                                                                                         |
|                    [`dataDictionaries`](#datadictionaries)                     |         |    ❌     | `List<Object>` |                     | Configure data dictionary<br />Since `2.4.6`, you can configure the interface implemented by the enumeration. When configuring the interface, the title will be used Description of the class that implements the enumeration. If there are already implemented enumerations that need to be ignored, you can add `@ignore` to the class that implements the enumeration to ignore them.                                                                                                                                     |
|               [`errorCodeDictionaries`](#errorcodedictionaries)                |         |    ❌     | `List<Object>` |                     | Error code list<br />Since `2.4.6`, the interface implemented by the enumeration can be configured. When configuring the interface, the title will be used Description of the class that implements the enumeration. If there are already implemented enumerations that need to be ignored, you can add `@ignore` to the class that implements the enumeration to ignore them.                                                                                                                                               |
|                        [`revisionLogs`](#revisionlogs)                         |         |    ❌     | `List<Object>` |                     | Document change record.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|                [`customResponseFields`](#customresponsefields)                 |         |    ❌     | `List<Object>` |                     | Customize added fields and comments, general users deal with third-party `jar` package libraries.                                                                                                                                                                                                                                                                                                                                                                                                                            |
|                 [`customRequestFields`](#customrequestfields)                  |         |    ❌     | `List<Object>` |                     | Comments for the custom request body.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|   [`requestHeaders`](/guide/advanced/advancedFeatures#public-request-header)   | `2.1.3` |    ❌     | `List<Object>` |                     | Set public request headers.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| [`requestParams`](/guide/advanced/advancedFeatures#public-request-parameters)  | `2.2.3` |    ❌     | `List<Object>` |                     | Public request parameters (scenarios handled by interceptors).                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|                  [`rpcApiDependencies`](#rpcapidependencies)                   |         |    ❌     | `List<Object>` |                     | The project's open `Dubbo API` interface module depends on it. After configuration, it is output to the document to facilitate user integration.                                                                                                                                                                                                                                                                                                                                                                             |
|                              `rpcConsumerConfig`                               |         |    ❌     | `String`       |                     | The `Dubbo Consumer` integration configuration is added to the document to facilitate quick integration by the integrator.                                                                                                                                                                                                                                                                                                                                                                                                   |
|               [`apiObjectReplacements`](#apiobjectreplacements)                | `1.8.5` |    ❌     | `List<Object>` |                     | Use custom classes to override other classes for document rendering.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| [`apiConstants`](/guide/advanced/advancedFeatures#static-constant-replacement) | `1.8.9` |    ❌     | `List<Object>` |                     | Configure your own constant class, `smart-doc` resolves to constants automatically replaced with a specific value. Starting from `2.4.2` version, there is no need to configure constants when using them. `smart-doc` can already be automatically parsed.                                                                                                                                                                                                                                                                  |
|                  [`responseBodyAdvice`](#responsebodyadvice)                   | `1.8.9` |    ❌     | `List<Object>` |                     | `ResponseBodyAdvice` is a hook reserved in the `Spring` framework, which acts after the execution of the `Controller` method is completed After that, before the `http` response body is written back to the client, it can easily weave in some of its own business logic processing, so `smart-doc` also provides unified return settings for `ResponseBodyAdvice` (do not configure it casually according to the project technology to configure) support, which can be ignored using the `ignoreResponseBodyAdvice` tag. |
|                   [`requestBodyAdvice`](#requestbodyadvice)                    | `2.1.4` |    ❌     | `List<Object>` |                     | Set the `RequestBodyAdvice` unified request wrapper class.                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|                              [`groups`](#groups)                               | `2.2.5` |    ❌     | `List<Object>` |                     | Group different `Controllers`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|                              `requestParamsTable`                              | `2.2.5` |    ❌     | `String`       |                     | Whether to display the request parameter table in the document.                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|                             `responseParamsTable`                              | `2.2.5` |    ❌     | `Boolean`      |                     | Whether to display the response parameter table in the document.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                                  `framework`                                   | `2.2.5` |    ❌     | `String`       | `spring` or `dubbo` | `Spring` and `Apache Dubbo` are frameworks that support parsing and generating documents by `smart-doc` by default and are not configured` framework` automatically selects `Spring` or `Dubbo` according to the triggered document construction scenario. `smart-doc` currently also supports the `JAX-RS` standard, so use a framework that supports the `JAX-RS` standard (such as: ` Quarkus`) can be used as an experience, but it is not complete yet. <br />Optional values: `spring`, `dubbo`, `JAX-RS`, `solon`     |
|                                  `randomMock`                                  | `2.6.9` |    ❌     | `Boolean`      |       `false`       | `randomMock` is used to control whether `smart-doc` generates random `mock` values, in versions before `2.6.9` `smart-doc` will automatically assign parameters and automatically generate random values. The generated values are different each time. Now you can set it to `false` to control the generation of random values.                                                                                                                                                                                            |
|                                `componentType`                                 | `2.7.8` |    ❌     | `String`       |      `RANDOM`       | `openapi component key generator`<br />`RANDOM`: supports `@Validated` group verification<br />`NORMAL` : Does not support `@Validated`, used for `openapi` generated code                                                                                                                                                                                                                                                                                                                                                   |
|                                `apiUploadNums`                                 | `3.0.2` |    ❌     | `Integer`      |                     | When uploading `Torna`, batch uploading of documents is supported, and the size of document batches can be set.                                                                                                                                                                                                                                                                                                                                                                                                              |
|                                `showValidation`                                | `3.0.3` |    ❌     | `Boolean`      |       `true`        | `showValidation` is used to control whether `smart-doc` extracts the JSR validation information of fields for display in the documentation.                                                                                                                                                                                                                                                                                                                                                                                  |
|                                    `jmeter`                                    | `3.0.4` |    ❌     | `Object`       |                     | Custom Configurations for JMeter Performance Test Script Generation                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|                            `addDefaultHttpStatuses`                            | `3.0.5` |    ❌     | `Boolean`      |       `false`       | When generating documentation, consider whether to include the default HTTP status codes from frameworks such as Spring MVC's default `500` and `404` errors. Currently, only the generation of `OpenAPI` documentation supports this feature.                                                                                                                                                                                                                                                                               |
|                                `enumConvertor`                                 | `3.1.0` |    ❌     | `Boolean`      |       `false`       | In the header/path/query request mode, whether to enable the enumeration converter, The default value is false. <br/>If true, the enumeration value is parsed as an enumeration example value. <br/>If false, take the enumeration name as the enumeration example value                                                                                                                                                                                                                                                     |
|                              `allowSelfReference`                              | `3.1.1` |    ❌     | `Boolean`      |       `false`       | Whether to enable self-reference handling, default value is false.<br/>Enables recursive expansion of self-referencing structures up to 2 levels.<br/>When enabled, self-referencing fields (like `List<T> children`) will display full structure instead of empty or reference-only content.                                                                                                                     |
|                  [`openApiTagNameType`](#openapitagnametype)                   | `3.1.1` |    ❌     | `String`       |    `CLASS_NAME`     | Determines how to generate tag names (`tags[].name`) in the OpenAPI document. Possible values: <ul><li>`CLASS_NAME` (default): Use the controller's simple class name.</li><li>`DESCRIPTION`: Use the controller's description.</li><li>`PACKAGE_NAME`: Use the controller's full package name.</li></ul> This setting controls how API operations are grouped in the OpenAPI documentation.                                                                                                                                 |

```json
{
    "serverUrl": "http://127.0.0.1",
    "serverEnv": "http://{{server}}",
    "pathPrefix": "",
    "isStrict": false,
    "allInOne": true,
    "outPath": "D://md2",
    "randomMock": false,
    "coverOld": true,
    "createDebugPage": true,
    "packageFilters": "",
    "packageExcludeFilters": "",
    "md5EncryptedHtmlName": false,
    "style": "xt256",
    "projectName": "smart-doc",
    "framework": "spring",
    "skipTransientField": true,
    "serializeRequestTransients": false,
    "serializeResponseTransients": false,
    "sortByTitle": false,
    "showAuthor": true,
    "requestFieldToUnderline": true,
    "responseFieldToUnderline": true,
    "inlineEnum": true,
    "recursionLimit": 7,
    "allInOneDocFileName": "index.html",
    "requestExample": "true",
    "responseExample": "true",
    "requestParamsTable": true,
    "responseParamsTable": true,
    "urlSuffix": ".do",
    "displayActualType": false,
    "appToken": "c16931fa6590483fb7a4e85340fcbfef",
    "isReplace": true,
    "openUrl": "http://localhost:7700/api",
    "debugEnvName": "Test ENV",
    "debugEnvUrl": "http://127.0.0.1",
    "tornaDebug": false,
    "author": "smart-doc",
    "increment": false,
    "ignoreRequestParams": [
        "org.springframework.ui.ModelMap"
    ],
    "dataDictionaries": [
        {
            "title": "http status",
            "enumClassName": "com.power.common.enums.HttpCodeEnum",
            "codeField": "code",
            "descField": "message"
        },
        {
            "enumClassName": "com.xx.IEnum",
            "codeField": "code",
            "descField": "message"
        }
    ],
    "errorCodeDictionaries": [
        {
            "title": "title",
            "enumClassName": "com.power.common.enums.HttpCodeEnum",
            "codeField": "code",
            "descField": "message",
            "valuesResolverClass": ""
        },
        {
            "enumClassName": "com.xx.IEnum",
            "codeField": "code",
            "descField": "message"
        }
    ],
    "revisionLogs": [
        {
            "version": "1.0",
            "revisionTime": "2020-12-31 10:30",
            "status": "update",
            "author": "author",
            "remarks": "desc"
        }
    ],
    "customResponseFields": [
        {
            "name": "code",
            "desc": "response code",
            "ownerClassName": "org.springframework.data.domain.Pageable",
            "ignore": true,
            "value": "00000"
        }
    ],
    "customRequestFields": [
        {
            "name": "code",
            "desc": "status code",
            "ownerClassName": "com.xxx.constant.entity.Result",
            "value": "200",
            "required": true,
            "ignore": false
        }
    ],
    "requestHeaders": [
        {
            "name": "token",
            "type": "string",
            "desc": "desc",
            "value": "token value",
            "required": false,
            "since": "-",
            "pathPatterns": "/app/test/**",
            "excludePathPatterns": "/app/page/**"
        },
        {
            "name": "appkey",
            "type": "string",
            "desc": "desc",
            "value": "appkey value",
            "required": false,
            "pathPatterns": "/test/add,/testConstants/1.0",
            "since": "-"
        }
    ],
    "requestParams": [
        {
            "name": "configPathParam",
            "type": "string",
            "desc": "desc",
            "paramIn": "path",
            "value": "testPath",
            "required": false,
            "since": "-",
            "pathPatterns": "/**",
            "excludePathPatterns": "/app/page/**"
        },
        {
            "name": "configQueryParam",
            "type": "string",
            "desc": "desc",
            "paramIn": "query",
            "value": "testQuery",
            "required": false,
            "since": "-",
            "pathPatterns": "/**",
            "excludePathPatterns": "/app/page/**"
        }
    ],
    "rpcApiDependencies": [
        {
            "artifactId": "SpringBoot2-Dubbo-Api",
            "groupId": "com.demo",
            "version": "1.0.0"
        }
    ],
    "rpcConsumerConfig": "src/main/resources/consumer-example.conf",
    "apiObjectReplacements": [
        {
            "className": "org.springframework.data.domain.Pageable",
            "replacementClassName": "com.power.doc.model.PageRequestDto"
        }
    ],
    "apiConstants": [
        {
            "constantsClassName": "com.power.doc.constants.RequestParamConstant"
        }
    ],
    "responseBodyAdvice": {
        "className": "com.power.common.model.CommonResult"
    },
    "requestBodyAdvice": {
        "className": "com.power.common.model.CommonResult"
    },
    "groups": [
        {
            "name": "test group",
            "apis": "com.power.doc.controller.app.*"
        }
    ],
    "requestParamsTable": true,
    "responseParamsTable": true,
    "componentType": "RANDOM",
    "jmeter": {
        "addPrometheusListener": true
    },
    "addDefaultHttpStatuses": true,
    "enumConvertor": false,
    "allowSelfReference": false,
    "openApiTagNameType": "CLASS_NAME"
}
```
## packageFilters

`Controller` packet filtering, multiple packets are separated by commas.

> PS: Starting from 2.2.2, you need to use regular rules: com.test.controller.*, and starting from 2.7.1, you need to use method-level regular rules: com.test.controller.TestController.*
```json
{
    "packageFilters": "com.test.controller.*", // Output all interfaces under the controller package
    "packageFilters": "com.example.controller.PetController", // Only output the interface of PetController
    "packageFilters": "com.example.controller.*Controller", // Output all interfaces under the controller package with the Controller suffix as the class name
    "packageFilters": "com.example.controller.Pet.*", // Output all interfaces under the controller package that have class names starting with Pet
    "packageFilters": "com.example.controller.Pet.*Controller", // Output all interfaces under the controller package that match the Pet*Controller class name
    "packageFilters": "com.example.controller.PetController.getPetInfo", // Output the getPetInfo method interface in PetController
    "packageFilters": "com.example.controller.PetController.*", // Output all interfaces in PetController
    "packageFilters": "com.example.controller.PetController.get.*", // Only output all interfaces in the PetController class that start with get as the method name
    "packageFilters": "com.example.controller.PetController.*Info", //Only output all interfaces in the PetController class whose method names end with Info
    "packageFilters": "com.example.controller.PetController.get.*Info", //Only output all interfaces in the PetController class that match get.*Info as the method name
}
```

If the interface filtering result does not meet expectations after configuration, the issue might be in the regular expression setup. You can manually invoke the `DocUtil` tool in `smart-doc` to verify your regex.

Refer to the following example for validation:

```
    /**
     * test packageFilters pattern
     */
    @Test
    void testIsMatchPattern() {
        String classOne = "xxx.yyy.zzz.Controller";
        String classTwo = "xxx.yyy.zzz222.TestController";

        // Match only classes under com.example
        String packageFiltersOne = "^xxx\\.yyy\\.zzz\\..*$";
        boolean result1 = DocUtil.isMatch(packageFiltersOne, classOne);
        boolean result2 = DocUtil.isMatch(packageFiltersOne, classTwo);

        assertTrue(result1);
        assertFalse(result2);

        // Greedy regex with .*
        String packageFiltersTwo = "xxx.yyy.zzz.*";
        boolean result3 = DocUtil.isMatch(packageFiltersTwo, classOne);
        boolean result4 = DocUtil.isMatch(packageFiltersTwo, classTwo);

        assertTrue(result3);
        assertTrue(result4);
    }
```



## dataDictionaries

Configure the data dictionary. Starting from `2.4.6`, you can configure the interface implemented by the enumeration. When configuring the interface, `title` will use the class description that implements the enumeration. If there are already implemented enumerations that need to be ignored, you can implement the enumeration. Add `@ignore` to the class to ignore it.

| Configuration   | Type     | Description                                                                                                                                                                                                                                                    |
|-----------------|----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `title`         | `String` |                                                                                                                                                                                                                                                                |
| `enumClassName` | `String` | Error code enumeration class                                                                                                                                                                                                                                   |
| `codeField`     | `String` | The name of the `code` code field of the error code. By default, `smart-doc` uses the `getCode` method name to obtain it through reflection. If there is no `get` method, you can configure the corresponding method name of the field, for example: `code()`. |
| `descField`     | `String` | The field name corresponding to the error code description information. Like `codeField`, it can be configured as a method name, for example: `message()`                                                                                                      |

```json
{
    "dataDictionaries": [
        {
            "title": "title",
            "enumClassName": "com.power.common.enums.HttpCodeEnum", 
            "codeField": "code", 
            "descField": "message" 
        }
    ]
}
```



## errorCodeDictionaries

Error code list, starting from `2.4.6`, you can configure the interface implemented by the enumeration. When configuring the interface, `title` will use the class description that implements the enumeration. If there are already implemented enumerations that need to be ignored, you can implement the enumeration. Add `@ignore` to the class to ignore it.

| Configuration   | Type     | Description                                                                                                                                                                                                                                                    |
|-----------------|----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `title`         | `String` |                                                                                                                                                                                                                                                                |
| `enumClassName` | `String` | Error code enumeration class                                                                                                                                                                                                                                   |
| `codeField`     | `String` | The name of the `code` code field of the error code. By default, `smart-doc` uses the `getCode` method name to obtain it through reflection. If there is no `get` method, you can configure the corresponding method name of the field, for example: `code()`. |
| `descField`     | `String` | The field name corresponding to the error code description information. Like `codeField`, it can be configured as a method name, for example: `message()`                                                                                                      |

```json
{
    "errorCodeDictionaries": [
        {
            "title": "title",
            "enumClassName": "com.power.common.enums.HttpCodeEnum", 
            "codeField": "code", 
            "descField": "message" 
        }
    ]
}
```



## revisionLogs

Documentation change history.

| Configuration  | Type     | Description                                            |
|----------------|----------|--------------------------------------------------------|
| `version`      | `String` | Document version number                                |
| `revisionTime` | `String` | Document revision time                                 |
| `status`       | `String` | Change operation status, usually: create, update, etc. |
| `author`       | `String` | Document change author                                 |
| `remarks`      | `String` | Change description                                     |

```json
{
    "revisionLogs": [
        {
            "version": "1.0", 
            "revisionTime": "2020-12-31 10:30", 
            "status": "update", 
            "author": "author", 
            "remarks": "desc" 
        }
    ]
}
```



## customResponseFields

Customize added fields and comments, and general users deal with third-party `jar` package libraries.

| Configuration    | Type      | Description                                                                    |
|------------------|-----------|--------------------------------------------------------------------------------|
| `name`           | `String`  | Override response code field                                                   |
| `desc`           | `String`  | Field comments that override the response code                                 |
| `ownerClassName` | `String`  | Specify the class name you want to annotate                                    |
| `ignore`         | `Boolean` | Setting true will be automatically ignored and will not appear in the document |
| `value`          | `String`  | Set the value of the response code                                             |

```json
{
    "customResponseFields": [
        {
            "name": "code", 
            "desc": "response code", 
            "ownerClassName": "org.springframework.data.domain.Pageable",
            "ignore": true, 
            "value": "00000" 
        }
    ]
}
```



## customRequestFields

Customize added fields and comments, and general users deal with third-party `jar` package libraries.

| Configuration    | Type      | Description                                               |
|------------------|-----------|-----------------------------------------------------------|
| `name`           | `String`  | Property name                                             |
| `desc`           | `String`  | Description                                               |
| `ownerClassName` | `String`  | The full path of the class corresponding to the attribute |
| `ignore`         | `Boolean` | Whether to ignore                                         |
| `required`       | `Boolean` | Is it required                                            |
| `value`          | `String`  | Default value or mock value                               |

```json
{
    "customRequestFields": [
        {
            "name": "code", 
            "desc": "code", 
            "ownerClassName": "com.xxx.constant.entity.Result",
            "value": "200", 
            "required": true, 
            "ignore": false 
        }
    ]
}
```



## rpcApiDependencies

The open `Dubbo API` interface module of the project depends on it. After configuration, it is output to the document to facilitate user integration.

| Configuration | Type     | Description    |
|---------------|----------|----------------|
| `artifactId`  | `String` | `artifactId`   |
| `groupId`     | `String` | `groupId`      |
| `version`     | `String` | Version number |

```json
{
    "rpcApiDependencies": [
        {
            "artifactId": "SpringBoot2-Dubbo-Api",
            "groupId": "com.demo",
            "version": "1.0.0"
        }
    ]
}
```



## apiObjectReplacements

Use custom classes to override other classes for document rendering.

| Configuration          | Type     | Description                                   |
|------------------------|----------|-----------------------------------------------|
| `className`            | `String` | The full class name that needs to be replaced |
| `replacementClassName` | `String` | The fully qualified class name to be replaced |

```json
{
    "apiObjectReplacements": [
        {
            "className": "org.springframework.data.domain.Pageable",
            "replacementClassName": "com.power.doc.model.PageRequestDto" //自定义的PageRequestDto替换Pageable做文档渲染
        }
    ]
}
```



## responseBodyAdvice

`ResponseBodyAdvice` is a hook reserved in the `Spring` framework. It acts after the `Controller` method is executed and before the `http` response body is written back to the client. It can conveniently weave in some of its own business logic processing. Therefore, `smart-doc` also provides support for unified return settings of `ResponseBodyAdvice` (do not configure it casually according to the technology of the project), which can be ignored by `ignoreResponseBodyAdvice` `tag`.

| Configuration | Type     | Description             |
|---------------|----------|-------------------------|
| `className`   | `String` | Universal response body |

```json
{
    "responseBodyAdvice": {
        "className": "com.power.common.model.CommonResult" 
    }
}
```



## requestBodyAdvice

Set the `RequestBodyAdvice` unified request wrapper class.

| Configuration | Type     | Description            |
|---------------|----------|------------------------|
| `className`   | `String` | Universal request body |

```json
{
    "requestBodyAdvice": {
        "className": "com.power.common.model.CommonResult" 
    }
}
```



## groups

Group different `Controllers`.

> PS: Grouping does not take effect on postman.json and openApi.json

| Configuration | Type     | Description                                                                           |
|---------------|----------|---------------------------------------------------------------------------------------|
| `name`        | `String` | Group name                                                                            |
| `apis`        | `String` | Group url, supports regular expressions,with multiple expressions separated by commas |

```json
{
  "groups": [
    {
      "name": "Test Group",
      "apis": "com.example.controller.*",
      "apis": "com.example.controller.PetController", // Contains only the interface of PetController
      "apis": "com.example.controller.Controller", // Contains all interfaces under the controller package with a class name suffixed by Controller
      "apis": "com.example.controller.Pet.", // Contains all interfaces under the controller package with a class name starting with Pet
      "apis": "com.example.controller.Pet.Controller" // Contains all interfaces under the controller package that match the class name PetController
    }
  ]
}
```
If the `apis` configuration does not take effect in templates that support grouping, there might be an issue with the regular expression configuration. You can validate this using the `DocUtil` tool in `smart-doc`.

Here is an example of how to verify:

```
@Test
public void testIsMatch() {
    String pattern = "com.aaa.*.controller";
    String controllerName = "com.aaa.cc.controlle";
    System.out.println(DocUtil.isMatch(pattern, controllerName));
}
```
## jmeter    <Badge type="tip" text="^3.0.4" />
Starting from version `3.0.4`, the following custom configuration options have been added when generating `JMeter` performance test scripts:

| Configuration           | Type      | Description                                                       |
|-------------------------|-----------|-------------------------------------------------------------------|
| `addPrometheusListener` | `Boolean` | Whether to add a `Prometheus` listener when generating the script |

```json
{
  "jmeter": {
    "addPrometheusListener": true
  }
}
```

## openApiTagNameType <Badge type="tip" text="^3.1.1" />

Added in version `3.1.1`, this configuration controls the **generation strategy for `tags[].name` in OpenAPI documents**. It allows flexible definition of how API interfaces are grouped in the documentation.

### ✅ Configuration Details

| Configuration        | Type     | Description                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `openApiTagNameType` | `String` | Specifies the tag name generation method. Supported enumeration values:<br> - `CLASS_NAME` (default): Uses the controller class name as the tag name (e.g., `UserController`)<br> - `DESCRIPTION`: Uses the controller description as the tag name (e.g., `User Management Interface`)<br> - `PACKAGE_NAME`: Uses the full package path of the controller (e.g., `com.example.controller`) |

### 📄 Example Configuration

```json
{
  "openApiTagNameType": "DESCRIPTION"
}
```

### 📌 Usage Guide

- **CLASS_NAME**  
  Uses the controller class name directly as the tag name. Suitable for basic scenarios.  
  Example: `UserController` → Tag name `UserController`

- **DESCRIPTION**  
  Uses the controller's description
  Example: Description set to `User Management Interface` → Tag name `User Management Interface`

- **PACKAGE_NAME**  
  Uses the full package path as the tag name. Ideal for modular organization in large projects.  
  Example: Package path `com.example.controller.user` → Tag name `com.example.controller.user`

### 🧩 Recommended Scenarios

| Scenario                            | Recommended Configuration | Description                           |
|-------------------------------------|---------------------------|---------------------------------------|
| Quickly generate base documentation | `CLASS_NAME`              | No extra configuration required       |
| Use user-friendly tag names         | `DESCRIPTION`             | Leverage controller descriptions      |
| Organize documentation by module    | `PACKAGE_NAME`            | Logical grouping by package structure |

































































