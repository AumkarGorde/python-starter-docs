# Related To Types
- `from __future__ import annotations`
```
class Node:
    def __init__(self, value: int, next: "Node" = None):
        self.value = value
        self.next = next

```
- Without the from __ future __ import , we must use a string literal `"Node"` to refer the class itself as a forward reference, because `Node` is not fully defined yet
- With the use of __ future __, python stores all the annotations as string, deferring their evaluation later
```
from __future__ import annotations

class Node:
    def __init__(self, value: int, next: Node | None = None):
        self.value = value
        self.next = next

```