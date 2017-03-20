---
title: VNJS Documentation
---

## VNJS Documentation

### About

VNJS is an engine for creating interactive visual stories for publishing on the Web, using HTML5.

```javascript
function Parser(rules, start) {
    var table = this.table = [];
    this.rules = rules.map(function (r) { return (new Rule(r.name, r.symbols, r.postprocess)); });
    this.start = start = start || this.rules[0].name;
    // Setup a table
    var addedRules = [];
    this.table.push([]);
    // I could be expecting anything.
    this.rules.forEach(function (r) {
        if (r.name === start) {  // add all rules named start
            addedRules.push(r);
            table[0].push(new State(r, 0, 0));
        }});  // this should refer to this object, not each rule inside the forEach
    this.advanceTo(0, addedRules);
    this.current = 0;
}
```
