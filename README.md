<!--
https://readme42.com
-->



[![](https://img.shields.io/badge/OS-Unix-blue.svg?longCache=True)]()
[![](https://img.shields.io/pypi/v/postgres-mktempdb.svg?maxAge=3600)](https://pypi.org/project/postgres-mktempdb/)
[![](https://img.shields.io/npm/v/postgres-mktempdb.svg?maxAge=3600)](https://www.npmjs.com/package/postgres-mktempdb)[![](https://img.shields.io/badge/License-Unlicense-blue.svg?longCache=True)](https://unlicense.org/)
[![](https://github.com/andrewp-as-is/postgres-mktempdb/workflows/tests42/badge.svg)](https://github.com/andrewp-as-is/postgres-mktempdb/actions)

### Installation
```bash
$ [sudo] pip install postgres-mktempdb
```

```bash
$ [sudo] npm i -g postgres-mktempdb
```

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
    <a href="https://readme42.com/">readme42.com</a>
</p>
