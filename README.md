# Principle of API definition.

## Never do case sensitive.

WWW is not a case sensitive world.
URLs are case insensitive.
It is only confusing to distinguish upper case letters and lower case letters from users in the world of WWW.
Adopting "Camel case" is valid only with class names such as java.
Even if there are special reasons, "Snake case" should be used.

## Must set version.

I do not necessarily need to expose the version in the URL, but the domestic API should also be aware of the version of the API management side.
There are two clear indicators to expose versions.
First, it is necessary to make the API exposed to the public, to make the version visible to the URL in the API group that others can build the service using the API, to make the user aware.
The second case is when the provider of the API needs to include the master data etc. to use the API.
In this case, because it is domestic use, it is not necessarily necessary to expose the version.
It is a good idea to internally maintain the version corresponding to the connection source in the mechanism of authentication and authorization when providing the API.

## Response may be an objective.

Rules are required for API requests and responses.
If there are no special reasons, there is no choice other than JSON at present.
For example, by always outputting "is_succeeded", "status_code", etc. to each API, you can let the user decide whether it is normal or an error.
However, items other than always output should be objective.
For example, "smartphone_number" and "smartphone_type" should not be defined as sibling elements.
"number" and "type" should be defined in the "smartphone" object.
Although JSON is a very easy-to-use language, it is not good to verify the values of sibling elements, since loop processing is always required to confirm sibling elements.
Also, when developing additional APIs, it is useful to rule out that it is an objective so that people such as "smartphone_kind" are not output by considering future maintenance costs.

To be continued.

Thanks!
