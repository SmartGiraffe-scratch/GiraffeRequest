import json
import os

class JSONDatabase:
    def __init__(self, filename):
        self.filename = filename
        if not os.path.exists(filename):
            with open(filename, 'w') as f:
                json.dump({}, f)

    def add_update(self, key, value, parent=None):
        with open(self.filename, 'r+') as f:
            data = json.load(f)
            if parent is None:
                data[key] = value
            else:
                parent_data = data
                for p in parent.split('.'):
                    if p not in parent_data:
                        parent_data[p] = {}
                    parent_data = parent_data[p]
                parent_data[key] = value
            f.seek(0)
            json.dump(data, f, indent=4)
            f.truncate()

    def read(self, key, parent=None):
        with open(self.filename, 'r') as f:
            data = json.load(f)
            if parent is None:
                return data.get(key)
            else:
                parent_data = data
                for p in parent.split('.'):
                    if p not in parent_data:
                        return None
                    parent_data = parent_data[p]
                return parent_data.get(key)

    def get_keys(self, parent=None):
        with open(self.filename, 'r') as f:
            data = json.load(f)
            if parent is None:
                return list(data.keys())
            else:
                parent_data = data
                for p in parent.split('.'):
                    if p not in parent_data:
                        return []
                    parent_data = parent_data[p]
                return list(parent_data.keys())
