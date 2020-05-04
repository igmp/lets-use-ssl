Describe your SSL certificates here, one certificate per file.  Make sure your files have a valid
YAML extension: `yml` or `yaml`.  Format is as follows:
```yaml
example.com:
  alt_names:
    - "*.example.com"
    - high.level.example.com
```

Actually you can place multiple certificates in one file:
```yaml
foo.example.com:
  alt_names:
    - bar.example.com

foo.example.org:
  alt_names:
    - bar.example.org
```

The `alt_names` parameter is optional:
```yaml
foo.example.com:
```

If you are using 3rd level public domains, such as `example.com.ru`, state its real zone name as well:
```yaml
example.com.ru:
  zone: example.com.ru
  alt_names:
    - "*.example.com.ru"
```
Otherwise we'll try to put DNS challenges into the corresponding 2nd level zone
and this is obviously not what you want.
