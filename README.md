# wp-plugin-tracker
Plugin tracking for WordPress installations on cPanel. This is finds WordPress
installations by looking for any table in any database that looks like
WordPress 'options' tables, and then tries to pull WordPress information from
that table and then from the filesystem. This is very fast *when compared* to
crawling the filesystem to find WordPress installations.

This is a single Perl script that creates a single SQLite file from scratch on
each run to contain server-local information about WordPress plugins, not a
larger system for multiple servers.

# usage
```
# ./wpscan

# sqlite3 /var/lib/wp/plugins.sqlite .schema
CREATE TABLE plugins (
        host TEXT NOT NULL,
        db TEXT NOT NULL,
        tbl TEXT NOT NULL,
        user TEXT NOT NULL,
        siteurl TEXT NOT NULL,
        root TEXT NOT NULL,
        wpver TEXT NOT NULL,
        ppath TEXT NOT NULL,
        plugin TEXT NOT NULL,
        pver TEXT NOT NULL,
        suspended INT NOT NULL,
        theme TEXT NOT NULL
);
```
