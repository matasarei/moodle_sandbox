> [!IMPORTANT]
> This repo is obsolete no longer supported, try this instead: https://gist.github.com/matasarei/d9e10ab2572d629311b19fdc41138093

# Moodle sandbox
Moodle test and development environment.

## Requirements 
* docker (recommended version `18.03.0` or later);
* docker-compose (recommended vertion `1.13.0` ro later).

## Installation
1. Clone this repo
   ```
   $ git clone git@github.com:matasarei/moodle_sandbox.git
   $ cd moodle_sandbox
   ```

2. Clone Moodle repo: `git clone -b MOODLE_35_STABLE git@github.com:moodle/moodle.git`

3. Build and up containers: `docker-compose up -d`

4. Navigate to http://<moodle_host>:8080/ (replace `<moodle_host>` with real hostname or IP, like `localhost` or `127.0.0.1`)

5. Select database type: `MariaDB (native/mariadb)`

6. Use next database configudation:
* db host:     `mariadb`
* db name:     `moodle`
* db user:     `moodle`
* db password: `q2w3e4r5`

Use `docker-compose stop \ start` to stop or \ and start sandbox.

## Versions
Supported Moodle version >= 3.1. For older verions (<= 3.0) try `legacy` branch (with PHP5).

## How to use external directory

Create `docker-compose.override.yml` with next content:
```yaml
version: "3"
services:
    
  moodle:
    volumes:
      - <your_moodle_dir_absolute_path>:/var/www/moodle
```
