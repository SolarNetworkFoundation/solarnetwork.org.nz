# SolarNetwork Foundation Hugo website source

The `home` directory contains the source for the SolarNetwork Foundation
website, using the [Hugo][hugo] content generation tool.

## Developer server

To run the Hugo developer web server, **including** draft content, run `hugo`
like this:

```sh
cd home
hugo server -D --uglyURLs
```

## Staging build

To build for staging, **including** draft content, run `hugo` like this:

```sh
cd home
rm -rf public && hugo -D --uglyURLs
```

The website will be generated in the `public/` directory.

## Production build

To build for production, **excluding** draft content, run `hugo` like this:

```sh
cd home
sed -i '' -e 's/stage.solarnetwork.org.nz/solarnetwork.org.nz/g' config.toml
rm -rf public && hugo --uglyURLs
git checkout config.toml
```

This will modify the `config.toml` file to point to the production URL, run Hugo
to generate the website, and then undo the change to `config.toml`.

The website will be generated in the `public/` directory.


 [hugo]: https://gohugo.io/
