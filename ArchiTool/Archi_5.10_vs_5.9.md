# Archi 5.10 Functionality Compares with 5.9

- [Archi 5.10 Functionality Compares with 5.9](#archi-510-functionality-compares-with-59)
  - [Overview of Testing](#overview-of-testing)
  - [New Features](#new-features)
    - [N01. Add Markdown/HTML support for documentation fields in Properties tab and HTML reports](#n01-add-markdownhtml-support-for-documentation-fields-in-properties-tab-and-html-reports)
    - [N02. Add “Quick Add” popup dialog in ArchiMate Views (Alt+click and Shift+A shortcuts)](#n02-add-quick-add-popup-dialog-in-archimate-views-altclick-and-shifta-shortcuts)
    - [N03. Support for SVG image format in diagram figures](#n03-support-for-svg-image-format-in-diagram-figures)
    - [N04. Support multi-monitor display scaling on Windows (Eclipse)](#n04-support-multi-monitor-display-scaling-on-windows-eclipse)
    - [N05. Add zoom support to the Visualiser](#n05-add-zoom-support-to-the-visualiser)
    - [N06. Add “Manhattan Router” option for connections to the Visualiser](#n06-add-manhattan-router-option-for-connections-to-the-visualiser)
    - [N07. Zoom in diagrams now centres on the mouse cursor location](#n07-zoom-in-diagrams-now-centres-on-the-mouse-cursor-location)
    - [N08. New grid display in diagrams](#n08-new-grid-display-in-diagrams)
    - [N09. Add new option for connection label offset (North, South, East, etc.)](#n09-add-new-option-for-connection-label-offset-north-south-east-etc)
    - [N10. New selection and drag outline figures](#n10-new-selection-and-drag-outline-figures)
    - [N11. Allow Aggregation/Composition connections from Grouping/Location to Junction](#n11-allow-aggregationcomposition-connections-from-groupinglocation-to-junction)
    - [N12. Add relationships to the “ArchiMate Relationships” dialog](#n12-add-relationships-to-the-archimate-relationships-dialog)
    - [N13. Add Clear Cache button for Edge browser in preferences on Windows](#n13-add-clear-cache-button-for-edge-browser-in-preferences-on-windows)
    - [N14. Import ArchiMate exchange format creates a bendpoint on connection for sourceAttachment and targetAttachment](#n14-import-archimate-exchange-format-creates-a-bendpoint-on-connection-for-sourceattachment-and-targetattachment)
    - [N15. Add a preference to show a circle indicator in tabs rather than an asterisk for unsaved changes](#n15-add-a-preference-to-show-a-circle-indicator-in-tabs-rather-than-an-asterisk-for-unsaved-changes)
  - [Improvements](#improvements)
  - [Fixes](#fixes)

## Overview of Testing

Parallel run Archi 5.9.0 (installed package) and 5.10.0 (extracted zip package)

| Archi 5.9.0 Build: 202604140726 | Archi 5.10.0 Build: 202609031246 |
| --- | --- |
| ![archi5.9.0about](img/archi5.9.0.png) | ![archi5.10.0about](img/archi5.10.0.png) |

The new model will be created in each version for apple-to-apple comparison, when comparing, the left screen will be v5.9.0, and the right screen will be v5.10.0.

> [!Tip]
> You may see the test model file name as `test5.9.archimate` vs. `test5.10.archimate` for distinguishing.

## New Features

### N01. Add Markdown/HTML support for documentation fields in Properties tab and HTML reports

Using following as the test Documentation for one sample element - capability:

===START===

`# Marketing`

`## Marketing Level 2`

**Bold Text** with *Italic Text*.

<h2>HTML Title</h2>

```python
print("hello world!)
```

URL: https://www.google.com

Here is the normal text

===END===

When you are writing (editing) the content in the Documentation area, no difference between v5.9.0 and v5.10.0, however, notice the "eye" icon in below highlighted in v5.10.0:

![5.10_n01_1](img/5.10_n01_1.png)

When you click the "eye" icon (`View`), in v5.10.0, you can directly see the rendered content following both Markdown and HTML, as below:

![5.10_n01_2](img/5.10_n01_2.png)

The icon is now changed to a "pen", which can be toggled between `Edit` and `View`.

Export both model to HTML report, below you can see the HTML element documentation in v5.10.0 is shown under Markdown and HTML syntax:

![5.10_n01_3-html](img/5.10_n01_3-html.png)

**Add-on for Reference**: the new release doesn't mention change in Jasper report, indeed, you cannot get the same experience of Markdown/HTML support in Jasper as of in HTML report, however, below I've exported the test model to Jasper reports, and compare their HTML file, you may see slightly difference:

![5.10_n01_4-jasper](img/5.10_n01_4-jasper.png)

### N02. Add “Quick Add” popup dialog in ArchiMate Views (Alt+click and Shift+A shortcuts)

In v5.9.0, you need to drag an element icon from Palette to add it into the view; this new feature in v5.10.0 allows you to use `Alt+Click` (Click the view area) or `Shift+A` (click the view area first to activate "focus" to the view) to pop up one element palette list dialog:

![5.10_n02](img/5.10_n02.png)

Select one target element then double-click to add into the view.

If you want to use one existing element, still `drag and drop` from model tree,.

### N03. Support for SVG image format in diagram figures

I see both v5.9.0 and v5.10.0 can support SVG as the exported view image format, as below:

![5.10_n03](img/5.10_n03.png)

### N04. Support multi-monitor display scaling on Windows (Eclipse)

Not see specific, will keep monitor.

### N05. Add zoom support to the Visualiser

In v5.10.0, inside Visualiser area, use `Ctrl` + mouse' scroll-wheel to adjust, there're 7 levels of zoom-in and zoom-out.

`Ctrl+0` will back to the original zoom level, from this level you can have -2 (zoom-out) to +5 (zoom-in) changes.

![5.10_n05](img/5.10_n05.png)

### N06. Add “Manhattan Router” option for connections to the Visualiser

| v5.9.0 | v5.10.0|
| --- | --- |
| ![5.9_n06](img/5.9_n06.png) | ![5.10_n06](img/5.10_n06.png) |

After click the `Manhattan Router`, the connection line will be changes in v5.10.0:

![5.10_n06-1](img/5.10_n06-1.png)

This is one toggle setting, click it again will restore the original style:

![5.10_n06-2](img/5.10_n06-2.png)

### N07. Zoom in diagrams now centres on the mouse cursor location

Do not see the behavior difference between v5.9.0 and v5.10.0.

### N08. New grid display in diagrams

![5.10_n08](img/5.10_n08.png)

### N09. Add new option for connection label offset (North, South, East, etc.)

### N10. New selection and drag outline figures

### N11. Allow Aggregation/Composition connections from Grouping/Location to Junction

### N12. Add relationships to the “ArchiMate Relationships” dialog

### N13. Add Clear Cache button for Edge browser in preferences on Windows

### N14. Import ArchiMate exchange format creates a bendpoint on connection for sourceAttachment and targetAttachment

### N15. Add a preference to show a circle indicator in tabs rather than an asterisk for unsaved changes

## Improvements

I01. Built on Eclipse 4.40 and the latest Eclipse GEF/Draw2d frameworks

I02. Bundled Java Runtime is version 21.0.11+10

I03. Improvements to rendering of diagram figures

I04. A figure’s width and height is no longer 1 pixel short due to fixes in GEF/Draw2d

I05. Use a tooltip to display the parent folder paths in “Used in Views” and “Model Relations” analysis tables

I06. Update themes to the latest Eclipse versions

I07. The “Classic” theme has been removed as it’s no longer supported in Eclipse 4.40 and later

I08. The round tabs option has been removed from appearance preferences as it’s no longer supported in Eclipse 4.40 and later

I09. The focused element’s node in the Visualiser has an italic font to differentiate it

I10. Improve calculation of some connection anchors

I11. Improvements to link regex parsing in text fields

I12. Archi version 4.x to 5.x automatic migrator removed

I13. Set text position to bottom for some types in figure type preview

I14. Improved columns widths in the “ArchiMate Relationships” dialog

I15. Select All action in Tree views now updates the selection in other views

I16. Improvements to diagram scale calculation

I17. Improved handling of ArchiMate relationship rules

I18. Added support for future handling of derived and direct relationships

I19. Remove unnecessary “p2/org.eclipse.equinox.p2.core”, “org.eclipse.equinox.p2.engine/.settings” and “org.eclipse.equinox.p2.repository” directories from build

I20. Improvements to error logging

I21. Improvements to menu handling so that plug-ins can contribute to the main “View” menu

I22. Update Jasper Reports Fonts library to version 6.21.4 – fixes some issues with emojis and other characters

I23. [HTML Report] Update StringTemplate library to version 4.3.4 – fixes some issues with emojis and other characters

I24. [HTML Report] Update jQuery to version 3.7.1

## Fixes

F01. Fix “Delete From Model” not deleting all connected relationships

F02. Ensure that only one Specialization is set for a Concept

F03. Fix connection not highlighted blue when hovering with connection creation tool or magic connector

F04. Fix possible image export not using display scaling when switching from 100% dislay to higher display scales

F05. Fix possible exception in Templates Manager

F06. Many fixes in the Eclipse frameworks

F07. Many internal fixes and optimisations

---

Last updated at 2026-10-21