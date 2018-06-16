# Moodle sandbox
Moodle test and development environment.

## Requirements 
* docker (recommended version `18.03.1-ce, build 9ee9f40` or later);
* docker-compose (recommended vertion `1.21.2, build a133471` ro lated).
 
## Installation

1. Clone repo: `git clone -b MOODLE_35_STABLE git@github.com:moodle/moodle.git`;

2. Build and up containers: `docker-compose up -d --build`;

3. Navigate to http://<moodle_host>:8080/ (replace `<moodle_host>` with real host, like `localhost`);

4. Select database type: `MariaDB (native/mariadb)`;

5. Use next values:
* db host:     `mariadb`
* db name:     `moodle`
* db user:     `moodle`
* db password: `q2w3e4r5`

## How to use external directory

Create `docker-compose.override.yml` with next content:
```yaml
version: "3"
services:
    
  moodle:
    volumes:
      - <your_moodle_dir_absolute_path>:/var/www/moodle
```
