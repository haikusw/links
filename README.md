Reference
===

- AppleDoc
  -  Comments formatting style doc:
      https://github.com/tomaz/appledoc/blob/master/CommentsFormattingStyle.markdown

  - NSHipster quickie:
      http://nshipster.com/documentation/

  - Apple Naming conventions
  https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/CodingGuidelines/Articles/NamingBasics.html#//apple_ref/doc/uid/20001281-BBCHBFAH


   
Code
===

- Discount - C implementation of Markdown (supposedly what AppleDoc uses internally)
  http://www.pell.portland.or.us/%7Eorc/Code/discount/

- AppleDoc
  https://github.com/tomaz/appledoc


- msgpack - compressed/binary JSON replacement 
  http://msgpack.org

- xctool
  https://github.com/facebook/xctool/


Online Tools
===

- c gibberish <-> english  :)
  http://cdecl.org

Tools
===

- Xcode plug-in package manager
  https://github.com/supermarin/Alcatraz

- VVDocumenter-Xcode documentation generator plug-in
  https://github.com/onevcat/VVDocumenter-Xcode


Random tidbits to remember
===

- XCTest - http://nshipster.com/xctestcase/
   XCTAssert[Not]EqualWithAccuracy for comparing two Double, Float, or other floating point values.
  ```
    XCTAssertEqualWithAccuracy(expression1, expression2, accuracy, format...)
    XCTAssertNotEqualWithAccuracy(expression1, expression2, accuracy, format...)
  ```
   Performance testing:
    ``` 
    [self.measureBlock: ^{
      // do something
      }];
    ```
   Asynchronous testing via `XCTestExpectation`
      https://developer.apple.com/library/ios/documentation/DeveloperTools/Conceptual/testing_with_xcode/testing_3_writing_test_classes/testing_3_writing_test_classes.html#//apple_ref/doc/uid/TP40014132-CH4-SW6
      `XCTestExpectation`, `XCTestExpectation::fulfill`, and `XCTestExpectation::waitForExpectationsWithTimout:handler:`
   

- lldb tips
  - $arg1, $arg2, $arg3, ..., $arg9 for command/method arguments (1 = self, 2 = _cmd for objC methods of course).
  - use in conditional breakpoints:  
      br s -S setObject:forKey: -c '($arg3 == nil)'

