# BottomSheet

Bring to SwiftUI the UIKit bottom sheet capabilities that came with iOS15.

## About fork

This fork brings additional parameter to [prevent dismissal](https://sarunw.com/posts/bottom-sheet-in-ios-15-with-uisheetpresentationcontroller/#prevent-dismissal).

## Usage

#### Show the bottom sheet

``` swift
Button(action: { show.toggle() }) {
    Text("Show!")
}
.bottomSheet(
    isPresented: $show,
    detents: .mediumAndLarge,
    shouldScrollExpandSheet: true,
    modalInPresentation: false,
    largestUndimmedDetent: .medium,
    showGrabber: true,
    cornerRadius: 20
) {
    List {
        Section {
            ForEach(0..<50, id: \.self) { id in
                Text("Item \(id)")
            }
        } header: {
            Text("Look at that bottom sheet!!")
        }
    }
}
```

#### Dismiss

``` swift
Button(action: { BottomSheet.dismiss() }) {
    Label("Dismiss", systemImage: "multiply")
}
```

## Preview

![Bottom sheet](./bottomsheet.gif)

## Sources

Inspired by Sarun W.'s article ["How to present a Bottom Sheet in iOS 15 with UISheetPresentationController"](https://sarunw.com/posts/bottom-sheet-in-ios-15-with-uisheetpresentationcontroller/).
