# WorldSync2
World Sync is an object position and rotation finder within a 3d space for situations of limited network compatibiltiy within some unity games.

If your application uses a social aspect such as avatars a system like this may be useful for your application.

WorldSync operates on a small Finite State Machine. 

It operates by creating a miniature copy of your base character relative to the World/Scene. This copy moves at 1/127th the normal rate in each direction.

The position is then found via a Binary Search Tree in each planar direction.

It is first found on a macro (127^2) +- 16129. Then Coarse +-127 and then +- Precise 127/127 (with a 1/127 precision).

The reason for 127 is due to having 8 bits of memory to transmit a float. So we only have 255 spaces to use. So +-127 with 0 inbetween.