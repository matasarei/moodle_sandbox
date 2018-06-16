# Moodle sandbox
Moodle test and development environment.

## Requirements 
* docker (recommended version `18.03.0` or later);
* docker-compose (recommended vertion `1.13.0` ro lated).
 
## Installation
1. Clone this repo

2. Clone Moodle repo: `git clone -b MOODLE_35_STABLE git@github.com:moodle/moodle.git`

3. Build and up containers: `docker-compose up -d --build`

4. Navigate to http://<moodle_host>:8080/ (replace `<moodle_host>` with real host, like `localhost`)

5. Select database type: `MariaDB (native/mariadb)`

6. Use next values:
* db host:     `mariadb`
* db name:     `moodle`
* db user:     `moodle`
* db password: `q2w3e4r5`

Use `docker-compose stop \ start` to stop and start sandbox.

## How to use external directory

Create `docker-compose.override.yml` with next content:
```yaml
version: "3"
services:
    
  moodle:
    volumes:
      - <your_moodle_dir_absolute_path>:/var/www/moodle
```
