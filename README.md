# NAME

Plack::Middleware::TrailingSlashKiller - Dealing with that pesky trailing slash/

# SYNOPSIS

    builder {
      enable "TrailingSlashKiller",
        redirect => 1
    };

# DESCRIPTION

`Plack::Middleware::TrailingSlashKiller` will look for trailing slashes
in the requested URL and remove them. Based on the `redirect` option,
it will either redirect or silently rewrite the URL before passing
it on to the app.

This module was written with [Dancer2](https://metacpan.org/pod/Dancer2) in mind, where `/path` and
`/path/` are different (and the latter usually results in a 404).

# PARAMETERS

- redirect

    This boolean will instruct the module to either return 301 (GET/HEAD)
    and 307 (other) results with a Location header or to silently rewrite
    the URL without a trailing slash.

# SEE ALSO

[Plack::Middleware](https://metacpan.org/pod/Plack::Middleware)

# AUTHOR

Menno Blom <blom@cpan.org>

# COPYRIGHT

Copyright 2015- Menno Blom

# LICENSE

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.
