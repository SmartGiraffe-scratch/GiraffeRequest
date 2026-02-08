# GiraffeRequest
Scratchattach configured to match -SmartGiraffe-'s needs

---

## Getting started with *json_db*
```python
from json_db import JSONDatabase

db=JSONDatabase("filename")
db.add_update("key", "worth", "parent")
print(db.read("key", "parent")) #returns string: "worth"
print(db.get_keys("parent")) #returns list of strings: ["key"]
```
`parent` seperates with `.` meaning you can get structures like this `parent.under`
---
