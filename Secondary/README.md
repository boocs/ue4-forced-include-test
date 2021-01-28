### UE4 Forced Include Test

This project uses relative paths for easier testing. UE4 doesn't use them though.

This test project doesn't mimic UE4 fully. If it did then Main would also error.

The difference could be because the forced include in UE4 contains a #include file that has over 600+ #include files. Perhaps it's some timing issue with so many includes and a recursive path in includePath.

Hopefully this test project will still help understand what is going on.

---
### Testing this project
Click on SharedPCH.Engine.ShadowErrors.h to get Intellisense errors.

The Main workspace's c_cpp_properties is commented on what works and what doesn't. You can uncomment and comment certain lines for testing.

---
### More UE4 project info

Something I discovered in the UE4 project:

Let's say the include error is in Game.h.

The 2nd error is for "GenericPlatform/ICursor.h" and it has to do with SharedPCH.Engine.ShadowErrors.h.

*Without messing with the includePath setting*: If you add #include "GenericPlatform/ICursor.h" to Game.h then that error will go away.

I believe the source/headers that don't error, in UE4, already #include everything that SharedPCH.Engine.ShadowErrors.h needs so there are no errors because of this. 
