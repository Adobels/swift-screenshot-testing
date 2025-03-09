# swift-screenshot-testing

The idea is to build a framework that captures snapshots of view controllers in UI test targets and snapshots controller views using unit tests.

Snapshotting view controllers using UI tests allows for out-of-the-box capturing of different states while awaiting asynchronous code completion. Escaping closures, Combine Futures, and Unstructured Concurrency Tasks can be awaited easily.

Dedicated UI test targets can present view controllers using deep-link techniques or Playbook-style presentation.

Screenshotting within unit tests should provide techniques for out-of-the-box support for escaping closures, Combine Future publishers, and Unstructured Concurrency Tasks. For example:

```swift
var isReadyForScreenshot = false

Task {
    defer { isReadyForScreenshot = true }
    // Perform async setup
}
```

An important part of development will focus on naming strategies and file hierarchy, for example, choosing between a flat structure or a tree structure that reflects test paths.

The first phase of development will focus on UIKit, with SwiftUI support added later.
