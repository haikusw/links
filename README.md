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

- chisel - lldb debugging aids for iOS
  https://github.com/facebook/chisel


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
      ```br s -S setObject:forKey: -c '($arg3 == nil)'```
    condition setting also works in Xcode visual breakpoint editor ``($arg3 == nil)``  (note no single quotes for Xcode UI)

- Format strings & NSInteger / NSUInteger
  - %tu (NSUInteger)
  - %zd (NSInteger)
  - %tx (hex output of NSUInteger/NSInteger)
  via https://twitter.com/gparker/status/377910611453046784 as of 9/2013


- Blocks cheat sheets
  - https://gist.github.com/haikusw/679c0818dbdb5970d5b8
  - http://goshdarnblocksyntax.com


git
===

`$ git fetch origin "+refs/heads/master:refs/remotes/origin/master" "+refs/pull/42/head:refs/pr/42"`
`$ git difftool "$(git merge-base origin/master pr/42)" pr/42`

`$ git config --global -l`

    difftool.sourcetree.cmd=opendiff "$LOCAL" "$REMOTE"
    difftool.sourcetree.path=
    mergetool.sourcetree.cmd=/Applications/SourceTree.app/Contents/Resources/opendiff-w.sh "$LOCAL" "$REMOTE" -ancestor "$BASE" -merge "$MERGED"
    mergetool.sourcetree.trustexitcode=true
    user.name=haikusw
    user.email= XXXXXXX
    mergetool.keepbackup=true
    difftool.Kaleidoscope.cmd=ksdiff --partial-changeset --relative-path "$MERGED" -- "$LOCAL" "$REMOTE"
    mergetool.Kaleidoscope.cmd=ksdiff --merge --output "$MERGED" --base "$BASE" -- "$LOCAL" --snapshot "$REMOTE" --snapshot
    mergetool.Kaleidoscope.trustexitcode=true
    mergetool.tower.cmd="/Applications/Tower.app/Contents/Resources/kaleidoscope.sh" "$LOCAL" "$REMOTE" "$BASE" "$MERGED"
    mergetool.tower.trustexitcode=true
    difftool.tower.cmd="/Applications/Tower.app/Contents/Resources/kaleidoscope.sh" "$LOCAL" "$REMOTE" "$MERGED"
    difftool.ksdiff.cmd=ksdiff --partial-changeset --relative-path "$MERGED" -- "$LOCAL" "$REMOTE"
    mergetool.ksdiff.cmd=ksdiff --merge --output "$MERGED" --base "$BASE" -- "$LOCAL" --snapshot "$REMOTE" --snapshot
    mergetool.ksdiff.trustexitcode=true
    diff.guitool=ksdiff
    diff.tool=twdiff
    difftool.twdiff.cmd=twdiff "$LOCAL" "$REMOTE"
    difftool.prompt=false

`git difftool branchname  -- working/path/to/file.m`
