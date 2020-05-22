# SolarNetwork Foundation Hugo website source

The `home` directory contains the source for the SolarNetwork Foundation
website, using the [Hugo][hugo] content generation tool.

## Developer server

To run the Hugo developer web server, **including** draft and future content, run `hugo`
like this:

```sh
cd home
hugo server -DF
```

## Staging build

To build for staging, **including** draft and future content, run `hugo` like this:

```sh
cd home
rm -rf public && hugo -DF
```

The website will be generated in the `public/` directory.

## Production build

To build for production, **excluding** draft content, run `hugo` like this:

```sh
cd home
rm -rf public && hugo --baseURL https://solarnetwork.org.nz/
```

The website will be generated in the `public/` directory.


 [hugo]: https://gohugo.io/
