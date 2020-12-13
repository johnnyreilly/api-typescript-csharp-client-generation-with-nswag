# Generate TypeScript and CSharp clients with NSwag based on an API

Generating clients for APIs is a tremendous way to reduce the amount of work you have to do when you're building a web project.  Why handwrite that code when it can be auto-generated for you by a tool like [NSwag](https://github.com/RicoSuter/NSwag)?

There's some great posts out there that show you how to generate these clients directly using an `nswag.json` file. This is a really great approach and [Sander Aernouts](https://github.com/sanderaernouts) has a [couple of great posts on this](https://github.com/sanderaernouts/autogenerate-api-client-with-nswag).

However, if you want to do some special customisation of the clients you're generating, you may find yourself struggling to configure that in `nswag.json`. In that case, it's possible to hook into NSwag directly to do this with a simple console app.

This post will:
- create a dot net API which exposes a Swagger endpoint
- create a dot net console app which can create both TypeScript and CSharp clients using the Swagger endpoint

You will need both [Node.js](https://nodejs.org/en/) and the [.NET SDK](https://dotnet.microsoft.com/download) installed.

#### Create an API

To create an API we'll drop to the command line and enter the following commands:

```shell
mkdir src
cd src
mkdir server-app
cd server-app
dotnet new api -o API
cd API
dotnet add package NSwag.AspNetCore
```


