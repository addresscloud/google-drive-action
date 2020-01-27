# google-drive-action

[![standard-readme compliant](https://img.shields.io/badge/standard--readme-OK-green.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

> An action to upload to Google Drive

## Table of Contents

- [Inputs](#inputs)
- [Usage](#usage)
- [Maintainers](#maintainers)
- [Contributing](#contributing)
- [License](#license)

## Inputs

### skicka-tokencache-json
`description` 'Content of `~/.skicka.tokencache.json` created by the `skicka` command'
`required` true

### upload-from
`description` 'The path where the files to upload are located'
`default` './'
`required` false

### upload-to
`description` 'The path where the files to be uploaded is located'
`required` true

### remove-outdated
`description` 'Whether to delete files that do not exist locally'
`default` 'true'
`required` false

### google-client-id
`description` Your Google Drive API client ID
`required` true

### google-client-secret
`description` Your Google Drive API client secret
`required` true

## Usage

```
- uses: addresscloud/google-drive-action@v1.0.0
  with:
    upload-from: ./My-file.pdf
    upload-to: /
    skicka-tokencache-json: ${{ secrets.FOO }}
    google-client-id: ${{ secrets.BAR }}
    google-client-secret: ${{ secrets.BAZ }}
```

## Maintainers

[@talltom](https://github.com/talltom)

## Contributing

### Create docker image

Refreshing image:

```sh
 docker build -t google-drive-action .
```

Docker login to GitHub:

```sh
echo TOKEN | docker login -u USERNAME --password-stdin docker.pkg.github.com
```

Tag the image:

```sh
docker tag IMAGE_ID docker.pkg.github.com/addresscloud/google-drive-action/google-drive-action:VERSION
```

Publish to GitHub:

```
docker push docker.pkg.github.com/addresscloud/google-drive-action/google-drive-action:VERSION
```

Small note: If editing the README, please conform to the [standard-readme](https://github.com/RichardLitt/standard-readme) specification.

## License

apl-2.0 © 2020 Merritt Krakowitzer
