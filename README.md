# Swift Package Sample

[![Build and test](https://github.com/boken-engine/swift-package-sample/actions/workflows/ios.yml/badge.svg)](https://github.com/boken-engine/swift-package-sample/actions/workflows/ios.yml)

Sample Swift Package to try `xcodebuild` commands.

Specially related to [this issue](https://github.com/boken-engine/boken-engine/issues/139).

## Requirements

Xcode version:

```s
% xcodebuild -version
Xcode 13.4.1
Build version 13F100
```

MacOs version: Monterey 12.4

## Commands

```s
% swift build
Building for debugging...
[2/2] Compiling swift_package_sample swift_package_sample.swift
Build complete! (3.57s)
```

Error trying to build without any argument:

```s
 % xcodebuild
2022-06-21 20:13:13.390 xcodebuild[7753:76682] Requested but did not find extension point with identifier Xcode.IDEKit.ExtensionSentinelHostApplications for extension Xcode.DebuggerFoundation.AppExtensionHosts.watchOS of plug-in com.apple.dt.IDEWatchSupportCore
2022-06-21 20:13:13.390 xcodebuild[7753:76682] Requested but did not find extension point with identifier Xcode.IDEKit.ExtensionPointIdentifierToBundleIdentifier for extension Xcode.DebuggerFoundation.AppExtensionToBundleIdentifierMap.watchOS of plug-in com.apple.dt.IDEWatchSupportCore
Command line invocation:
    /Applications/Xcode.app/Contents/Developer/usr/bin/xcodebuild

User defaults from command line:
    IDEPackageSupportUseBuiltinSCM = YES

xcodebuild: error: The directory /Users/josecelano/Documents/github/boken-engine/swift-package-sample does not contain an Xcode project.
```

```s
% xcodebuild -list
2022-06-21 20:21:22.470 xcodebuild[8332:81308] Requested but did not find extension point with identifier Xcode.IDEKit.ExtensionSentinelHostApplications for extension Xcode.DebuggerFoundation.AppExtensionHosts.watchOS of plug-in com.apple.dt.IDEWatchSupportCore
2022-06-21 20:21:22.470 xcodebuild[8332:81308] Requested but did not find extension point with identifier Xcode.IDEKit.ExtensionPointIdentifierToBundleIdentifier for extension Xcode.DebuggerFoundation.AppExtensionToBundleIdentifierMap.watchOS of plug-in com.apple.dt.IDEWatchSupportCore
Command line invocation:
    /Applications/Xcode.app/Contents/Developer/usr/bin/xcodebuild -list

User defaults from command line:
    IDEPackageSupportUseBuiltinSCM = YES

Resolve Package Graph

Resolved source packages:
  swift-package-sample: /Users/josecelano/Documents/github/boken-engine/swift-package-sample

Information about workspace "swift-package-sample":
    Schemes:
        swift-package-sample
```

Building succesfully with:

```s
xcodebuild -scheme swift-package-sample -destination "platform=iOS Simulator,OS=15.5,name=iPhone 13"
```

And:

```s
xcodebuild build-for-testing -scheme swift-package-sample -destination "platform=iOS Simulator,OS=15.5,name=iPhone 13"
```


## Links

- https://theswiftdev.com/swift-package-manager-tutorial/
- https://stackoverflow.com/questions/64540518/building-swift-package-manager-project-with-xcodebuild-how-to-ignore-xcodeproj