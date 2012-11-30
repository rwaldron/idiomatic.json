## Know JSON

JSON has a simple spec. Learn it.

The spec has some useful terminology. Objects have *pairs* and Arrays have *elements*.

## Idiomatic Style Guide

1. <a name="key-names">Key Names</a>
    - Use either lowerCamelCase or snake_case
    - Don't mix lowerCamelCase and snake_case in the same document
    - Use the same id key across an application (`id` and `_id` are popular choices for key names)
    - Avoid using really long key names. Any string can be a key in JSON, but

2. <a name="types">Extra Types</a>
    - JSON comes with a few simple types. Often applications need other types, like dates and
      symbols. It's also useful to note
    - Types for the most part should be contextually defined. If you need to store values of two
      different types, consider using different key names.
    - When you need to have a mix of things of different types, have a clear and obvious way of
      differentiating between types.
    - If the rules for types are complex, specify the types explicitly in the JSON, by wrapping
      values in objects, and using a pair to specify the type. For instance, if you had an array
      with dollars and pounds as strings, you might convert them from `["£8", "$15"]` to 
      `[{"type": "pounds", "value": 8}, {"type": "dollars", value: 15}]`.

3. <a name="dates">Dates</a>
    - Use ISO dates or UNIX timestamps for dates
    - Avoid unusual formats like the [ASP.net AJAX format](http://msdn.microsoft.com/en-us/library/bb299886.aspx#intro_to_json_sidebarb).

4. <a name="sets">Sets</a>
    - A set is like a JSON object (also called a hash) but with no values; only the keys.
    - There is no set type in JSON.
    - Arrays and objects are commonly used as sets. Be consistent in which you use. If you use
      objects, be consistent in what you use for the values.
    - If you're building an API and want it to be quick to read, a list may be the most
      intuitive. An example is tags for a blog post. `["programming", "json"]` reads easier
      than `{"programming": true, "json": true}`.
    - The object is more efficient when you're actually doing something with a set, but sometimes
      sets are moved around unmodified. For this a list will be more efficient.

5. <a name="complex-types">Complex Types</a>
    - A complex type is something like a location (latitude and longitude) or a link (text and url)
      that might take up two pairs in an object.

