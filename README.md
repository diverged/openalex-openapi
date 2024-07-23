# OpenAlex OpenAPI

This repository contains an unofficial OpenAPI 3.1.0 definition for the [OpenAlex API](https://docs.openalex.org/).

[OpenAlex.org](https://openalex.org/) provides access to a wealth of scholarly data, including information about authors, concepts, funders, institutions, publishers, sources, topics, and works.

## Development Status

At present, I cannot guarantee absolute correctness of this API definition.

Some disclaimers:

- My purpose in creating this definition was to learn OpenAPI, and to (hopefully) contribute something useful to Open Access along the way.
- I relied on the official OpenAlex [API docs](https://github.com/ourresearch/openalex-docs) and [Swagger 2.0 definition](https://github.com/ourresearch/openalex-api-docs/blob/0c3ed4dc58040b6802601a19a09bfec4b47e8cb4/source/spec.yaml) for reference, which are mildly incomplete and/or outdated in places.

What I *can* claim:

- This definition passes `openapi-generator validate` and `redocly lint` with zero errors and zero warnings.
- Go code generated with `openapi-generator` passes all of the [default tests generated](https://github.com/diverged/openalex-go-openapi31/blob/a3fd6ebc623c894615c421dfe1ba9d8fd3d7ed9b/test/api_default_test.go).
- I have been using Go client code generated from this successfully, including with the use of parameters like filter and sort.

I am continuing to add to and adjust the schema definitions as I encounter problems or response properties not yet documented in the official resources (e.g. relating to the new `topics` entities), but I am sure imperfections remain.

### Contributions

If you identify any problems, you are welcome to create an issue or a submit a pull request.  Either one would be appreciated!

## API Endpoints

The following endpoints are available in the OpenAlex API:

- `/authors`
- `/concepts`
- `/funders`
- `/institutions`
- `/keywords`
- `/publishers`
- `/sources`
- `/topics`
- `/works`
- `/autocomplete/{entity_type}`

## Parameters

The API supports various parameters to customize and filter the responses:

- `filter`: Apply filters to the results.
- `search`: Search for specific terms within the data.
- `sort`: Sort the results based on specified criteria.
- `page`: Specify the page number for paginated results.
- `per_page`: Define the number of results per page.
- `select`: Select specific fields to include in the response.
- `group_by`: Group the results by specified fields.
- `autocomplete`: Parameters for autocomplete functionality.
- `cursor`: Use cursor-based pagination.

## Security

The API supports an optional `PoliteEmail` security scheme, which allows users to include their email address in the request header for polite requests.

From the [OpenAlex docs](https://docs.openalex.org/how-to-use-the-api/rate-limits-and-authentication#the-polite-pool):
> The polite pool has much faster and more consistent response times. It's a good place to be.

Otherwise, OpenAlex requires no authentication at all for common pool requests.

## Components

The OpenAPI specification includes various components such as security schemes, schemas, and parameters, which are defined in separate files within the `components` directory.

## Usage

To use the OpenAlex API, refer to the `openapi.yaml` file for detailed information on the available endpoints, required parameters, and response formats.

## License

This project is made available under the [MIT license](https://github.com/diverged/openalex-openapi/blob/main/LICENSE).
