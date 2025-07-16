# Connect To Backend API

**Prompt:**

```
**Context:**  
- The `<component>` on `<page>` needs to be connected to the backend API endpoint `<HTTP_METHOD> <ENDPOINT_PATH>` as defined in the OpenAPI spec.

**Analysis:**  
- Identify the data flow: is this a data fetch (e.g. for a selector) or a data submit (e.g. for an input box)?
- Check the OpenAPI spec for request/response structure and validation.
- Determine what needs to change in the API client, controller, and template.

**Implementation:**  
- Update the API client and controller to fetch/submit data using the correct endpoint and data shape.
- Update the Nunjucks template to use dynamic data or submit to the backend.
- Handle errors and fallback UI as needed.
- Keep the code concise and reusable.


```

## Example Usage Of Prompt

> **Context:**  
> - The `fin-unit` selector` on `case-details` needs to be connected to the backend API endpoint `api/v1/reference/finishing-unit` as defined in the OpenAPI spec.
>
> **Analysis:**  
> - Identify the data flow: is this a data fetch (e.g. for a selector) or a data submit (e.g. for an input box)?
> - Check the OpenAPI spec for request/response structure and validation.
> - Determine what needs to change in the API client, controller, and template.
>
> **Implementation:**  
> - Update the API client and controller to fetch/submit data using the correct endpoint and data shape.
> - Update the Nunjucks template to use dynamic data or submit to the backend.
> - Handle errors and fallback UI as needed.
> - Keep the code concise and reusable.



---

[← Back to Prompt Library](../.)
