---
title: VNJS Documentation
---

## VNJS Documentation

### About

VNJS is an engine for creating interactive visual stories for publishing on the Web, using HTML5.

```javascript
  function (args, context) {
    var bg_element = context.getConstant('converse_background');
    context.setTargetStyle( bg_element, {
      y:720 + 75, alpha:0
    });
    context.animate(bg_element, { time:.5, easing: 'ease-in' });
  }
```
