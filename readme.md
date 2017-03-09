# IPython Async_magic

Async at the top level repl !

```python
In [1]: import aiohttp

In [2]: res = await aiohttp.get('https://api.github.com')
  File "<ipython-input-2-52b78a6e45a0>", line 1
    res = await aiohttp.get('https://api.github.com')
                      ^
SyntaxError: invalid syntax


In [3]: %load_ext async_magic

In [4]: res = %await aiohttp.get('https://api.github.com')

In [5]: await res.json()
Out[5]:
{'authorizations_url': 'https://api.github.com/authorizations',
 'code_search_url': 'https://api.github.com/search/code?q={query}{&page,per_page,sort,order}',
 'commit_search_url': 'https://api.github.com/search/commits?q={query}{&page,per_page,sort,order}',
 'current_user_authorizations_html_url': 'https://github.com/settings/connections/applications{/client_id}',
 'current_user_repositories_url': 'https://api.github.com/user/repos{?type,page,per_page,sort}',
 'current_user_url': 'https://api.github.com/user',
 'emails_url': 'https://api.github.com/user/emails',
 'emojis_url': 'https://api.github.com/emojis',
 ...
}
```

Note the `%` on assignments in `res = %await aiohttp.get('https://api.github.com')`

# Change loop:

Use `%loop <loop>`


