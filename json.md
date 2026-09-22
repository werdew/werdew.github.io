---
title: JSON
layout: default
nav_order: 14
---


# JSON

### Minimal skeleton (2020-12):

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "type": "object",
  "properties": {},
  "required": []
}
```

1. Root is almost always `"type": "object"` (or `"array"` if the whole payload is a list).
2. Every key in the example goes under `"properties"` (which is `"items"` if it's a list).
3. Set each value's data type:
    - `"string"`, `"number"`, `"integer"`, `"boolean"`, `"null"`
    - nested object → "type": `"object"` + its own `"properties"`
    - array → `"type": "array"` + `"items": { schema for one element }`
4. Put keys that must always be present in `"required"`.


