# GiraffeRequest
Scratchattach configured to match -SmartGiraffe-'s needs

---

## Getting started with *json_db*
```
from json_db import JSONDatabase

db=JSONDatabase("filename")
db.add_update("key", "worth", "parent")
print(db.read("key", "parent")) #returns "worth"
```
