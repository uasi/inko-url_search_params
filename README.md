# inko-url_search_params

An implementation of [the `URLSearchParams` class](https://url.spec.whatwg.org/#interface-urlsearchparams) from the URL Standard in the Inko programming language.

## Examples

    import url_search_params.UrlSearchParams

    let params = UrlSearchParams.from_string('a=A+A%26A&n=1&n=2')

    params.get('a') # => Option.Some('A A&A')
    params.get('x') # => Option.None
    params.get_all('n') # => ['1', '2']
    params.get_all('x') # => []

    # ---

    let params = UrlSearchParams.new

    params.set('a', 'will be overwritten')
    params.set('a', 'A A&A')
    params.append('n', '1')
    params.append('n', '2')

    params.to_string # => 'a=A+A%26A&n=1&n=2'
