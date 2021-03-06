# Photo Resources

    DELETE photos/:id/favorite

## Description
Removes the photo to user's list of favorites.

***

## Requires authentication
**[OAuth][]**

***

## Parameters

- **id** _(required)_ — ID of the photo to delete from list of favorites.

***

## Return format
A JSON object containing keys: **status**, **message** and **error**(if happened).

***

## Errors
All known errors cause the resource to return HTTP error code header together with a JSON array containing at least 'status' and 'error' keys describing the source of error.

- **400 Bad Request** — The request issued is missing one or more of the required parameters or contains parameters in an invalid form.
- **403 Forbidden** — The favorite request has been rejected; common reasons are: current user is inactive, has not completed their profile, or the photo is not in favorites list.
- **404 Not Found** — Photo with the specified ID does not exist.

***

## Example
**Request**

    DELETE /v1/photos/7942222/favorite

**Return**
``` json
{
  status: 200,
  message: "Successfully removed a favorite.",
  error: "None"
}
```

[OAuth]: https://github.com/500px/api-documentation/tree/master/authentication
[full format]: https://github.com/500px/api-documentation/blob/master/basics/formats_and_terms.md#full-format