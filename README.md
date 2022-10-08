# PHP Boilerplate

A highly opinionated repository with a collection of files to quickly spin up a PHP Project with sane defaults.
It is meant to make PHP Development painless. This setup is NOT meant for production.

# Vision

This repository should contain only the most common components like nginx, PHP, composer and a DB.
All less common setups will not be covered in this repo. I leave it up to you to configure and extend the setup.

If you are looking for a setup where everything is pre-installed, you might be better served by something like [Laradock](https://github.com/laradock/laradock)


# Getting Started

To get started clone the repo. Note: replace the `my-project` at end of the following command.

```sh
git clone --depth 1 https://github.com/Dmitrev/php-boilerplate.git my-project

```

## Delete files you don't need

Right now the only way to get the files is using git clone which also gets you a copy of the git folder, you will not need it, so you should delete it! 

```
rm -rf .git
```

## Run docker

```sh
docker compose up -d
```

## Optionally install framework

If you want to use something like laravel, just run this. This will install Laravel in `src/`

```sh
docker compose exec php composer create-project laravel/laravel .
```

# License

```
MIT License

Copyright (c) 2022 Dmitri Chebotarev 

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
