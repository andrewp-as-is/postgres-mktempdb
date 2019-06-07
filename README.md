<!--
https://pypi.org/project/readme-generator/
https://pypi.org/project/python-readme-generator/
-->

[![](https://img.shields.io/badge/OS-Unix-blue.svg?longCache=True)]()
[![](https://img.shields.io/pypi/v/postgres-mktempdb.svg?maxAge=3600)](https://pypi.org/project/postgres-mktempdb/)
[![](https://img.shields.io/npm/v/postgres-mktempdb.svg?maxAge=3600)](https://www.npmjs.com/package/postgres-mktempdb)
[![Travis](https://api.travis-ci.org/looking-for-a-job/postgres-mktempdb.svg?branch=master)](https://travis-ci.org/looking-for-a-job/postgres-mktempdb/)

#### Installation
```bash
$ [sudo] npm i -g postgres-mktempdb
```
```bash
$ [sudo] pip install postgres-mktempdb
```

#### Scripts usage
command|`usage`
-|-
`mktempdb` |`usage: mktempdb [OPTION]...`

#### Examples
```bash
$ mktempdb
tmp_LH8LqXy8UGlfMR8zfB3todrc4mwC9Sns
```

delete temp databases:
```bash
$ psql -At -c "SELECT datname FROM pg_database WHERE datname LIKE 'tmp_%'" | xargs -L 1 dropdb
```

delete temp databases created more than 5 minutes ago:
```bash
$ psql -At -c "SELECT datname FROM pg_database
WHERE datname LIKE 'tmp_%' AND (pg_stat_file('base/'||oid||'/PG_VERSION')).modification<now()+interval '5 minutes'" | xargs -L 1 dropdb
```

<p align="center">
    <a href="https://pypi.org/project/python-readme-generator/">python-readme-generator</a>
</p>