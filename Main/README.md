### UE4 Forced Include Test

This project uses relative paths for easier testing. UE4 doesn't use them though.

---
### Testing this project

1. Click on Main.h
   * Uncomment #include line to fix preinclude
   * Comment out the #include line

2. Open Main/.vscode/c_cpp_properties.json
   * Uncomment/comment lines to test
   * Line with ********* comment will get rid of errors
