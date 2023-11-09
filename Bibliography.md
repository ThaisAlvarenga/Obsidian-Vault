---
aliases:
  - references
---

Page to collect relevant bibliographies
```page-gallery
# Any options given at the root level of the configuration
# will be used as defaults for all views (but can be overridden
# in any individual view).
fields: [file.name]
columns: 3
orientation: landscape

# If you don't include an explicit `views` option (which needs
# to be an array), then page-gallery will just use all the root
# level options as a single unnamed view.
views:
  - name: References
    from: '"References"'
  - name: Narratology
    from: '"References" AND #Narratology' 
  - name: XR
    from: '"References/XR"'
  - name: Media Studies
    from: '#media-studies'
```
