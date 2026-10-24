# Archi 5.10 Functionality Compares with 5.9

- [Archi 5.10 Functionality Compares with 5.9](#archi-510-functionality-compares-with-59)
  - [Overview of Testing](#overview-of-testing)
  - [New Features](#new-features)
    - [\* N01. Add Markdown/HTML support for documentation fields in Properties tab and HTML reports](#-n01-add-markdownhtml-support-for-documentation-fields-in-properties-tab-and-html-reports)
    - [\* N02. Add “Quick Add” popup dialog in ArchiMate Views (Alt+click and Shift+A shortcuts)](#-n02-add-quick-add-popup-dialog-in-archimate-views-altclick-and-shifta-shortcuts)
    - [\* N03. Support for SVG image format in diagram figures](#-n03-support-for-svg-image-format-in-diagram-figures)
    - [N04. Support multi-monitor display scaling on Windows (Eclipse)](#n04-support-multi-monitor-display-scaling-on-windows-eclipse)
    - [\* N05. Add zoom support to the Visualiser](#-n05-add-zoom-support-to-the-visualiser)
    - [\* N06. Add “Manhattan Router” option for connections to the Visualiser](#-n06-add-manhattan-router-option-for-connections-to-the-visualiser)
    - [N07. Zoom in diagrams now centres on the mouse cursor location](#n07-zoom-in-diagrams-now-centres-on-the-mouse-cursor-location)
    - [\* N08. New grid display in diagrams](#-n08-new-grid-display-in-diagrams)
    - [\* N09. Add new option for connection label offset (North, South, East, etc.)](#-n09-add-new-option-for-connection-label-offset-north-south-east-etc)
    - [\* N10. New selection and drag outline figures](#-n10-new-selection-and-drag-outline-figures)
    - [\* N11. Allow Aggregation/Composition connections from Grouping/Location to Junction](#-n11-allow-aggregationcomposition-connections-from-groupinglocation-to-junction)
    - [\* N12. Add relationships to the “ArchiMate Relationships” dialog](#-n12-add-relationships-to-the-archimate-relationships-dialog)
    - [N13. Add Clear Cache button for Edge browser in preferences on Windows](#n13-add-clear-cache-button-for-edge-browser-in-preferences-on-windows)
    - [N14. Import ArchiMate exchange format creates a bendpoint on connection for sourceAttachment and targetAttachment](#n14-import-archimate-exchange-format-creates-a-bendpoint-on-connection-for-sourceattachment-and-targetattachment)
    - [N15. Add a preference to show a circle indicator in tabs rather than an asterisk for unsaved changes](#n15-add-a-preference-to-show-a-circle-indicator-in-tabs-rather-than-an-asterisk-for-unsaved-changes)
  - [Improvements](#improvements)
    - [I01. Built on Eclipse 4.40 and the latest Eclipse GEF/Draw2d frameworks](#i01-built-on-eclipse-440-and-the-latest-eclipse-gefdraw2d-frameworks)
    - [I02. Bundled Java Runtime is version 21.0.11+10](#i02-bundled-java-runtime-is-version-2101110)
    - [I03. Improvements to rendering of diagram figures](#i03-improvements-to-rendering-of-diagram-figures)
    - [I04. A figure’s width and height is no longer 1 pixel short due to fixes in GEF/Draw2d](#i04-a-figures-width-and-height-is-no-longer-1-pixel-short-due-to-fixes-in-gefdraw2d)
    - [I05. Use a tooltip to display the parent folder paths in “Used in Views” and “Model Relations” analysis tables](#i05-use-a-tooltip-to-display-the-parent-folder-paths-in-used-in-views-and-model-relations-analysis-tables)
      - [Tooltip - "Used in Views"](#tooltip---used-in-views)
      - [Tooltip - "Model Relations"](#tooltip---model-relations)
    - [I06. Update themes to the latest Eclipse versions](#i06-update-themes-to-the-latest-eclipse-versions)
    - [I07. The “Classic” theme has been removed as it’s no longer supported in Eclipse 4.40 and later](#i07-the-classic-theme-has-been-removed-as-its-no-longer-supported-in-eclipse-440-and-later)
    - [I08. The round tabs option has been removed from appearance preferences as it’s no longer supported in Eclipse 4.40 and later](#i08-the-round-tabs-option-has-been-removed-from-appearance-preferences-as-its-no-longer-supported-in-eclipse-440-and-later)
    - [I09. The focused element’s node in the Visualiser has an italic font to differentiate it](#i09-the-focused-elements-node-in-the-visualiser-has-an-italic-font-to-differentiate-it)
    - [I10. Improve calculation of some connection anchors](#i10-improve-calculation-of-some-connection-anchors)
    - [I11. Improvements to link regex parsing in text fields](#i11-improvements-to-link-regex-parsing-in-text-fields)
    - [I12. Archi version 4.x to 5.x automatic migrator removed](#i12-archi-version-4x-to-5x-automatic-migrator-removed)
    - [I13. Set text position to bottom for some types in figure type preview](#i13-set-text-position-to-bottom-for-some-types-in-figure-type-preview)
    - [I14. Improved columns widths in the “ArchiMate Relationships” dialog](#i14-improved-columns-widths-in-the-archimate-relationships-dialog)
    - [I15. Select All action in Tree views now updates the selection in other views](#i15-select-all-action-in-tree-views-now-updates-the-selection-in-other-views)
    - [I16. Improvements to diagram scale calculation](#i16-improvements-to-diagram-scale-calculation)
    - [I17. Improved handling of ArchiMate relationship rules](#i17-improved-handling-of-archimate-relationship-rules)
    - [I18. Added support for future handling of derived and direct relationships](#i18-added-support-for-future-handling-of-derived-and-direct-relationships)
    - [I19. Remove unnecessary “p2/org.eclipse.equinox.p2.core”, “org.eclipse.equinox.p2.engine/.settings” and “org.eclipse.equinox.p2.repository” directories from build](#i19-remove-unnecessary-p2orgeclipseequinoxp2core-orgeclipseequinoxp2enginesettings-and-orgeclipseequinoxp2repository-directories-from-build)
    - [I20. Improvements to error logging](#i20-improvements-to-error-logging)
    - [I21. Improvements to menu handling so that plug-ins can contribute to the main “View” menu](#i21-improvements-to-menu-handling-so-that-plug-ins-can-contribute-to-the-main-view-menu)
    - [I22. Update Jasper Reports Fonts library to version 6.21.4 – fixes some issues with emojis and other characters](#i22-update-jasper-reports-fonts-library-to-version-6214--fixes-some-issues-with-emojis-and-other-characters)
    - [I23. \[HTML Report\] Update StringTemplate library to version 4.3.4 – fixes some issues with emojis and other characters](#i23-html-report-update-stringtemplate-library-to-version-434--fixes-some-issues-with-emojis-and-other-characters)
    - [I24. \[HTML Report\] Update jQuery to version 3.7.1](#i24-html-report-update-jquery-to-version-371)
  - [Fixes](#fixes)
    - [F01. Fix “Delete From Model” not deleting all connected relationships](#f01-fix-delete-from-model-not-deleting-all-connected-relationships)
    - [F02. Ensure that only one Specialization is set for a Concept](#f02-ensure-that-only-one-specialization-is-set-for-a-concept)
    - [F03. Fix connection not highlighted blue when hovering with connection creation tool or magic connector](#f03-fix-connection-not-highlighted-blue-when-hovering-with-connection-creation-tool-or-magic-connector)
    - [F04. Fix possible image export not using display scaling when switching from 100% dislay to higher display scales](#f04-fix-possible-image-export-not-using-display-scaling-when-switching-from-100-dislay-to-higher-display-scales)
    - [F05. Fix possible exception in Templates Manager](#f05-fix-possible-exception-in-templates-manager)
    - [F06. Many fixes in the Eclipse frameworks](#f06-many-fixes-in-the-eclipse-frameworks)
    - [F07. Many internal fixes and optimisations](#f07-many-internal-fixes-and-optimisations)

## Overview of Testing

Archi 5.10 Release Post is here: https://www.archimatetool.com/blog/2026/09/03/archi-5-10/

Parallel run Archi 5.9.0 (installed package) and 5.10.0 (extracted zip package)

| Archi 5.9.0 Build: 202604140726 | Archi 5.10.0 Build: 202609031246 |
| --- | --- |
| ![archi5.9.0about](img/archi5.9.0.png) | ![archi5.10.0about](img/archi5.10.0.png) |

The new model will be created in each version for apple-to-apple comparison, when comparing, the left screen will be v5.9.0, and the right screen will be v5.10.0.

> [!Tip]
> You may see the test model file name as `test5.9.archimate` vs. `test5.10.archimate` for distinguishing.

## New Features

### * N01. Add Markdown/HTML support for documentation fields in Properties tab and HTML reports

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

### * N02. Add “Quick Add” popup dialog in ArchiMate Views (Alt+click and Shift+A shortcuts)

> Archi: "You can now also add elements to an ArchiMate View using the Quick Add popup. To open it, Alt-click where you want the element to appear, or use the default shortcut Shift+A. Type in the filter box to search for an element then press Enter or double-click to add it at the cursor’s location."

In v5.9.0, you need to drag an element icon from Palette to add it into the view; this new feature in v5.10.0 allows you to use `Alt+Click` (Click the view area) or `Shift+A` (click the view area first to activate "focus" to the view) to pop up one element palette list dialog:

![5.10_n02](img/5.10_n02.png)

Select one target element then double-click to add into the view.

If you want to use one existing element, still `drag and drop` from model tree,.

### * N03. Support for SVG image format in diagram figures

> Archi: "You can now use SVG images in figures. These are the images that can be used for Specializations and general images in Notes and Canvas objects. Using the SVG format means that the image can be scaled without loss of quality. The Archi 5.10 User Guide has more information in the section “SVG Support”."

I see both v5.9.0 and v5.10.0 can support SVG as the exported view image format, as below:

![5.10_n03](img/5.10_n03.png)

Find free SVG images: https://freesvg.org/

While, to this release, the change is in the `Specialization Manager`, when you create/edit one specialization element and press `Image` button then add one new image, the File-Open dialog will be appeared, and below you can see the difference:

| v5.9.0 | v5.10.0|
| --- | --- |
| `*.png,*.jpg,*.jpeg,*.gif,*.tif,*.tiff,*.bmp,*.ico` | `*.png,*.jpg,*.jpeg,*.gif,*.tif,*.tiff,*.bmp,*.ico` and added `*.svg` |
| ![N03-5.9.0](img/N03-5.9.0.png) | ![N03-5.10.0](img/N03-5.10.0.png) |

However, as below, I create two specialization, one in PNG and the other in SVG, the PNG is able to be displayed, but SVG is not:

![N03-5.10.0-SVG-not-shown](img/N03-5.10.0-SVG-not-shown.png)

### N04. Support multi-monitor display scaling on Windows (Eclipse)

> Archi: "This support is provided by using the latest Eclipse framework."

> [!Note]
> Check https://github.com/archimatetool/archi/issues/1238#issuecomment-4343473602 for more information.

Not see specific, will keep monitor.

### * N05. Add zoom support to the Visualiser

In v5.10.0, inside Visualiser area, use `Ctrl` + mouse' scroll-wheel to adjust, there're 7 levels of zoom-in and zoom-out.

`Ctrl+0` will back to the original zoom level, from this level you can have -2 (zoom-out) to +5 (zoom-in) changes.

![5.10_n05](img/5.10_n05.png)

### * N06. Add “Manhattan Router” option for connections to the Visualiser

| v5.9.0 | v5.10.0|
| --- | --- |
| ![5.9_n06](img/5.9_n06.png) | ![5.10_n06](img/5.10_n06.png) |

After click the `Manhattan Router`, the connection line will be changes in v5.10.0:

![5.10_n06-1](img/5.10_n06-1.png)

This is one toggle setting, click it again will restore the original style:

![5.10_n06-2](img/5.10_n06-2.png)

### N07. Zoom in diagrams now centres on the mouse cursor location

Do not see the behavior difference between v5.9.0 and v5.10.0.

### * N08. New grid display in diagrams

> Archi: "The grid in diagrams now uses a “hierarchical” display."

![5.10_n08](img/5.10_n08.png)

### * N09. Add new option for connection label offset (North, South, East, etc.)

> Archi: "There’s a new “Label Offset” adjustment for connections. This sets the relative position of the connection’s label if its position is “Middle”. This means that connection labels can be positioned away from the connection. Options are “Centre”, “North”, “South”, “East”, “West”, “North East”, “North West”, “South East”, and “South West”."

![5.10_n09](img/5.10_n09.png)

The 9 positions are indicated as below:

![5.10_n09-1](img/5.10_n09-1.png)

### * N10. New selection and drag outline figures

| v5.9.0 | v5.10.0 |
| --- | --- |
| Outline figure is gray-filled | Outline figure is blue-filled |
| ![N10-5.9.0](img/N10-5.9.0.png) | ![N10-5.10.0](img/N10-5.10.0.png) |

### * N11. Allow Aggregation/Composition connections from Grouping/Location to Junction

| | v5.9.0 | v5.10.0 |
| --- | --- | --- |
| | Only the existing relation | Add `Composed of` and `Aggregates` relation |
| Grouping | ![N11-5.9.0-grouping](img/N11-5.9.0-grouping.png) | ![N11-5.10.0-grouping](img/N11-5.10.0-grouping.png) |
| Location | ![N11-5.9.0-location](img/N11-5.9.0-location.png) | ![N11-5.10.0-location](img/N11-5.10.0-location.png) |

When you drag a group of elements including junction to a `Grouping`, by default, you will be pop-up the relationship as `Composition` as below:

- v5.9.0:
  ![N11-5.9.0-grouping-1](img/N11-5.9.0-grouping-1.png)

- 5.10.10:
  ![N11-5.10.0-grouping-1](img/N11-5.10.0-grouping-1.png)

Here you don't see the difference, however, now in v5.10.0, after you create the `Composes Of` relationship from the `Grouping` to the `Junction`, you can have all elements - including `Junction` - shown in the visualization, which means the correct relationship analysis result base on the view:

| v5.9.0 | v5.10.0 |
| --- | --- |
| `Junction` is invisible when analyzing `Grouping`'s composition relation | `Junction` is visible after added as `Composes Of` from `Grouping` |
| ![N11-5.9.0-grouping-2](img/N11-5.9.0-grouping-2.png) | ![N11-5.10.0-grouping-2](img/N11-5.10.0-grouping-2.png) |

### * N12. Add relationships to the “ArchiMate Relationships” dialog

![N12-5.9.0-5.10.0](img/N12-5.9.0-5.10.0.png)

Note from `Plateau`, `Location` and `Grouping` you now - in v5.10.0 - can have `Composition relation` and `Aggregation relation` to a relationship. (echo back to N11)

### N13. Add Clear Cache button for Edge browser in preferences on Windows

Not feel specific impact since I'm maining using Chrome.

### N14. Import ArchiMate exchange format creates a bendpoint on connection for sourceAttachment and targetAttachment

Open `ArchiSurance2025.archimate` in v5.9.0:

![N14_1-open-model-in-5.9.0](img/N14_1-open-model-in-5.9.0.png)

Select menu `[File] > [Export] > [Model to Open Exchange File...]`:

![N14_2-export-to-openexchange](img/N14_2-export-to-openexchange.png)

Give one exported file name:

![N14_3-openexchange](img/N14_3-openexchange.png)

> Not yet creating the difference comparison.

### N15. Add a preference to show a circle indicator in tabs rather than an asterisk for unsaved changes

By default, v5.10.0 is set as same as v5.9.0, when there're unsaved changes, the asterisk (*) is appeared in the test of the tab texts:

![N15-both-before](img/N15-both-before.png)

In v5.10.0, as below, one new option can be checked in `Edit > Preferences... > Appearance`, called `Show a circle in tabs to indicate unsaved changes`:

![N15-preferences](img/N15-preferences.png)

Once this option is checked and clicke `Apply and Close`, the appearance in v5.10.0 for unsaved changes is shown in tabs as below:

![N15-5.10.0-after](img/N15-5.10.0-after.png)

The circle's black color in the active tab is darker than the inactive tabs.

> [!Note]
> However, the `Use round tabs` option in v5.9.0 is not shown in v5.10.0

## Improvements

### I01. Built on Eclipse 4.40 and the latest Eclipse GEF/Draw2d frameworks

### I02. Bundled Java Runtime is version 21.0.11+10

From `Archi/jre/release` --

v5.9.0:

```text
IMPLEMENTOR="Eclipse Adoptium"
IMPLEMENTOR_VERSION="Temurin-21.0.9+10"
JAVA_RUNTIME_VERSION="21.0.9+10-LTS"
JAVA_VERSION="21.0.9"
JAVA_VERSION_DATE="2025-10-21"
LIBC="default"
MODULES="java.base java.compiler java.datatransfer java.xml java.prefs java.desktop java.instrument java.logging java.management java.security.sasl java.naming java.rmi java.management.rmi java.net.http java.scripting java.security.jgss java.transaction.xa java.sql java.sql.rowset java.xml.crypto java.se java.smartcardio jdk.accessibility jdk.internal.jvmstat jdk.attach jdk.charsets jdk.internal.opt jdk.zipfs jdk.compiler jdk.crypto.ec jdk.crypto.cryptoki jdk.crypto.mscapi jdk.dynalink jdk.internal.ed jdk.editpad jdk.hotspot.agent jdk.httpserver jdk.incubator.vector jdk.internal.le jdk.internal.vm.ci jdk.internal.vm.compiler jdk.internal.vm.compiler.management jdk.jartool jdk.javadoc jdk.jcmd jdk.management jdk.management.agent jdk.jconsole jdk.jdeps jdk.jdwp.agent jdk.jdi jdk.jfr jdk.jlink jdk.jpackage jdk.jshell jdk.jsobject jdk.jstatd jdk.localedata jdk.management.jfr jdk.naming.dns jdk.naming.rmi jdk.net jdk.nio.mapmode jdk.random jdk.sctp jdk.security.auth jdk.security.jgss jdk.unsupported jdk.unsupported.desktop jdk.xml.dom"
OS_ARCH="x86_64"
OS_NAME="Windows"
SOURCE=".:git:759062135b07"
BUILD_SOURCE="git:839fa0b45d809157cffd3dc8515aad262a4a1776"
BUILD_SOURCE_REPO="https://github.com/adoptium/temurin-build.git"
SOURCE_REPO="https://github.com/adoptium/jdk21u.git"
FULL_VERSION="21.0.9+10-LTS"
SEMANTIC_VERSION="21.0.9+10"
BUILD_INFO="OS: Windows Server 2022 Version: 10.0"
JVM_VARIANT="Hotspot"
JVM_VERSION="21.0.9+10-LTS"
IMAGE_TYPE="JRE"
```

v5.10.0:

```text
IMPLEMENTOR="Eclipse Adoptium"
IMPLEMENTOR_VERSION="Temurin-21.0.11+10"
JAVA_RUNTIME_VERSION="21.0.11+10-LTS"
JAVA_VERSION="21.0.11"
JAVA_VERSION_DATE="2026-04-21"
LIBC="default"
MODULES="java.base java.compiler java.datatransfer java.xml java.prefs java.desktop java.instrument java.logging java.management java.security.sasl java.naming java.rmi java.management.rmi java.net.http java.scripting java.security.jgss java.transaction.xa java.sql java.sql.rowset java.xml.crypto java.se java.smartcardio jdk.accessibility jdk.internal.jvmstat jdk.attach jdk.charsets jdk.internal.opt jdk.zipfs jdk.compiler jdk.crypto.ec jdk.crypto.cryptoki jdk.crypto.mscapi jdk.dynalink jdk.internal.ed jdk.editpad jdk.hotspot.agent jdk.httpserver jdk.incubator.vector jdk.internal.le jdk.internal.vm.ci jdk.internal.vm.compiler jdk.internal.vm.compiler.management jdk.jartool jdk.javadoc jdk.jcmd jdk.management jdk.management.agent jdk.jconsole jdk.jdeps jdk.jdwp.agent jdk.jdi jdk.jfr jdk.jlink jdk.jpackage jdk.jshell jdk.jsobject jdk.jstatd jdk.localedata jdk.management.jfr jdk.naming.dns jdk.naming.rmi jdk.net jdk.nio.mapmode jdk.random jdk.sctp jdk.security.auth jdk.security.jgss jdk.unsupported jdk.unsupported.desktop jdk.xml.dom"
OS_ARCH="x86_64"
OS_NAME="Windows"
SOURCE=".:git:254494ad7d75"
BUILD_SOURCE="git:a612825ee82a20ac872d60958c349854c1f29a8e"
BUILD_SOURCE_REPO="https://github.com/adoptium/temurin-build.git"
SOURCE_REPO="https://github.com/adoptium/jdk21u.git"
FULL_VERSION="21.0.11+10-LTS"
SEMANTIC_VERSION="21.0.11+10"
BUILD_INFO="OS: Windows Server 2022 Version: 10.0"
JVM_VARIANT="Hotspot"
JVM_VERSION="21.0.11+10-LTS"
IMAGE_TYPE="JRE"
```

### I03. Improvements to rendering of diagram figures

> Archi: "Improvements have been made to the rendering of figures thanks to using the latest Graphical Eclipse Framework. Notably, a figure’s width and height is no longer 1 pixel short in relation to the grid."

### I04. A figure’s width and height is no longer 1 pixel short due to fixes in GEF/Draw2d

Related to above I03.

### I05. Use a tooltip to display the parent folder paths in “Used in Views” and “Model Relations” analysis tables

#### Tooltip - "Used in Views"

This is very useful improvement, since in v5.9.0, the full folder structure is shown in "Used in Views" list, which makes difficult to see all detail view level names if the folders hierarchy is too deep.

v5.10.0 returns the display to just show View name itself, while adding tooltip so you can see the full folder structure when you hover mouse over specific view line.

For testing, in both version, create view `Sample View I05` under view folder named `I05`, drag some elements into the view, then observe from `Properties > Analysis`:

![I05_1-display](img/I05_1-display.png)

The `Marketing Management (Capability)` is used in two views, one view is under folder structure, in v5.9.0, the "Used in Views" list the full path, while in v5.10.0, only shows the view name.

When you put mouse hover on that view displayed name, in v5.9.0, nothing happens, while in v5.10.0, a tooltip pops up:

![I05_2-display-tooltip](img/I05_2-display-tooltip.png)

#### Tooltip - "Model Relations"

This behavior is also same in the name list of "Model Relations", as below, when you're creating large amounts of relationships, it would be also good practice to manage the relations into certain folder structure, this sample the `Composition Relation` is organized under one layer of Relations folder.

In v5.10.0, when selecting the Capability element, this relation is shown in the "Model Relations" list, the display is only the relation name instead of having the full path as v5.9.0, the tooltip is enabled so you can see the path while hover your mouse cursor over it:

![I05_3-display-relations-tooltip](img/I05_3-display-relations-tooltip.png)

### I06. Update themes to the latest Eclipse versions

### I07. The “Classic” theme has been removed as it’s no longer supported in Eclipse 4.40 and later

Choose `[Edit] > [Preferences] > [Appearance]`

| v5.9.0 | v5.10.0 |
| --- | --- |
| ![I07_5.9.0](img/I07_5.9.0.png) | ![I07_5.10.0](img/I07_5.10.0.png) |

### I08. The round tabs option has been removed from appearance preferences as it’s no longer supported in Eclipse 4.40 and later

Choose `[Edit] > [Preferences] > [Appearance]`

![I08](img/I08.png)

### I09. The focused element’s node in the Visualiser has an italic font to differentiate it

![I09](img/I09.png)

### I10. Improve calculation of some connection anchors

### I11. Improvements to link regex parsing in text fields

### I12. Archi version 4.x to 5.x automatic migrator removed

This is legacy compability improvement, no need to be tested from v5.9.0 to v5.10.0

### I13. Set text position to bottom for some types in figure type preview

### I14. Improved columns widths in the “ArchiMate Relationships” dialog

See from below comparison, in v5.9.0, you may double-click the column's edge line then it will be auto-arrange to smaller width, while in 5.10.0, it's by default the optimized width.

![I14](img/I14.png)

### I15. Select All action in Tree views now updates the selection in other views

### I16. Improvements to diagram scale calculation

### I17. Improved handling of ArchiMate relationship rules

### I18. Added support for future handling of derived and direct relationships

### I19. Remove unnecessary “p2/org.eclipse.equinox.p2.core”, “org.eclipse.equinox.p2.engine/.settings” and “org.eclipse.equinox.p2.repository” directories from build

### I20. Improvements to error logging

### I21. Improvements to menu handling so that plug-ins can contribute to the main “View” menu

### I22. Update Jasper Reports Fonts library to version 6.21.4 – fixes some issues with emojis and other characters

### I23. [HTML Report] Update StringTemplate library to version 4.3.4 – fixes some issues with emojis and other characters

### I24. [HTML Report] Update jQuery to version 3.7.1

## Fixes

### F01. Fix “Delete From Model” not deleting all connected relationships

### F02. Ensure that only one Specialization is set for a Concept

### F03. Fix connection not highlighted blue when hovering with connection creation tool or magic connector

### F04. Fix possible image export not using display scaling when switching from 100% dislay to higher display scales

### F05. Fix possible exception in Templates Manager

### F06. Many fixes in the Eclipse frameworks

### F07. Many internal fixes and optimisations

---

Last updated at 2026-10-24