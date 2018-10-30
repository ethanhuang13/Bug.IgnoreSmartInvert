# Bug.IgnoreSmartInvert

This sample project demos a bug of UIView.accessibilityIgnoresInvertColors.

When iOS 11/12 Smart Invert feature is on, set ignoring all UIViews with UIView.appearance() protocol, present then dismiss a view controller, the presenting view controller will ignore the ignoring setting.

Reproduce steps:

1. On an iOS 11 or 12 device, enable Smart Invert
2. Launch the app
3. In application(didFinishLaunchingWithOptions:), call UIView.appearance().accessibilityIgnoresInvertColors = true
4. Present a view controller
5. Dismiss the view controller

Expected:
Presenting view controller and its subviews ignore invert.

Actual:
Presenting view controller and its subviews become inverted colors.

Notes:
See video for demo:

![video](bug-ignore-invert-demo.m4v)