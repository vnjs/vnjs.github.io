---
title: VNJS Documentation
---

## VNJS Documentation

### About

VNJS is an engine for creating interactive visual stories for publishing on the Web, using HTML5.

```javascript
// Animation for when a text trail is removed from display,
const converse_trail_exit = {%
  function (args, context) {
    var bg_element = context.getConstant('converse_background');
    context.setTargetStyle( bg_element, {
      y:720 + 75, alpha:0
    });
    context.animate(bg_element, { time:.5, easing: 'ease-in' });
  }
%};
converse_trail_exit.registerConstant(converse_background);




define start {

  // The game starts here.
  preloadFont DEFAULT_FONT;

  // Set the default text trail,
  setDefaultTextTrail ( converse_trail,
                        enter: converse_trail_enter,
                        exit:  converse_trail_exit );

//  // Set up the main converse element,
//  call setupMainConverse trail:converse_trail;

  // The converse trail,
//  setStyle ( converse_background, alpha:1, x:'50%', y:720 - (CONVERSE_HEIGHT / 2) );
  setStyle ( converse_trail, alpha:1, x:'50%', y:720 - (CONVERSE_HEIGHT / 2) );

  // The test rectangle,
  setStyle ( test_rectangle, alpha:0, x:'50.5%', y:'73%', scale_x:1.9, scale_y:1.9 ); //, rotation:-.1 );

  setTargetStyle ( test_rectangle, alpha:1, x:'50%' );
  animate ( test_rectangle, time:2, easing: EASE_OUT );
  setTargetStyle ( test_rectangle, y:'45%' );
  animate ( test_rectangle, time:1.5, easing: bounce_easing_1 );
  setTargetStyle ( test_rectangle, scale_x:1, scale_y:1, rotation:0 );
  animate ( test_rectangle, time:2, easing: EASE_OUT );

  player_name = 'Toorvok';
  player_name2 = 'Toorvokin';

  // Make an announcement,
  // Wait until interact,
  announce trail:'default' "Hey, how's it going? What'ya doing ${player_name}? Are ya doing okay ${player_name2} or do you have a stick you can throw towards that excited dog?";

  announce trail:'default' "This is another text thing that shows some info after an interact happened! This is another text thing that shows some info after an interact happened! This is another text thing that shows some info after an interact happened!";

  announce trail:'default' continueAfter:3 "Hello World! Or Hello ${player_name}.";

}
```
