# Changelog
* This project generally follows [semantic versioning](https://semver.org/). For a version `x.y.z`, `x` means a major (backward incompatible) change, `y` means a minor (backward compatible) change, and `z` means a patch (bug fix). Few versions may not strictly follow this rule due to historical reasons, though.
* Versions before 1.0 are in initial development. APIs are not stable for these versions, even a `y` version can involve a breaking change, and only partial notable changes are summarized in this document. See full commit history in the source repository for details.
* Backend server requirement in this document refers to the version of [`webscrapbook` Python package](https://github.com/danny0838/pywebscrapbook) (or PyWebScrapBook).

## [1.5.4] - 2023-01-04
* Fixed encoding error when viewing a MAFF/HTZ document with non-UTF-8 encoding.

## [1.5.3] - 2022-12-26
* Fixed a potential error that a capture hangs during downloading.
* Improved some tooltips.

## [1.5.2] - 2022-12-12
* Fixed an error when the downloaded folder name happens to contain bad ending chars after cropping.
* Fixed infinite loop when the downloaded folder cannot be generated.
* Fixed missing error message when an error occurs during folder name determination.

## [1.5.1] - 2022-11-23
* Fixed an issue that the "attrs" property is ignored when the "value" property is set for the "insert" command of a capture helper.

## [1.5.0] - 2022-11-03
* Added support of more URL placeholders for `capture.saveFilename` option.
* Improved some tooltips.

## [1.4.3] - 2022-06-03
* Fixed an error of iterating document.adoptedStyleSheets during a capture for Firefox since 101.0b8.

## [1.4.2] - 2022-05-05
* Fixed an error of undefined document.adoptedStyleSheets during a capture for Firefox < 101.

## [1.4.1] - 2022-05-05
* Fixed an error of accessing document.adoptedStyleSheets during a capture for Firefox 101.

## [1.4.0] - 2022-03-12
* Added GUI for `NOSCRIPTs` capture option.
* Minor option groups in the options page are now collapsed by default.
* Fixed an issue that `on*` attributes are not correctly handled if `capture.styleInline` is `remove`.
* Fixed an issue that a unicode surrogate pair is not correctly handled during text cropping in certain cases.
* Fixed tooltips about filename length restriction.
* Fixed some issues of test code.
* Upgraded 3rd party libraries.

## [1.3.1] - 2022-02-19
* Fixed an issue that an item moved into another item through drag-and-drop is placed at top rather than the bottem.

## [1.3.0] - 2022-02-16
* Fixed an error when a capture is invoked from the context menu of a Firefox private window.
* Fixed an error when a capture is invoked from a private tab in Firefox for Android.
* Fixed an issue that the archive viewer doesn't open additional tabs for a MAFF with multiple web pages in a Firefox private window.
* Adjusted sidebar updating mechanism as a tentative fix for an issue that items get disappeared or misplaced after several move/link/copy operations.

## [1.2.0] - 2022-01-21
* Fixed an issue that some control chars in a filename causes a downloading error.
* Fixed the bad path rule filler for in-depth capture.
* Fixed an inaccurate error log message for a link with an invalid URL.
* Intermediate data is now cached using indexedDB when available in Firefox.

## [1.1.0] - 2022-01-06
* Fixed an issue that all tabs are treated as selected when performing a capture or so in a Chromium-based mobile browser.
* Disable drag-and-drop in a Chromium-based mobile browser to prevent an unfixed bug.
* Internal code optimization.

## [1.0.1] - 2021-12-22
* Fixed an issue that the sidebar scrolling point is reset when the tree refreshes.

## [1.0.0] - 2021-12-07
* Dropped support of legacy ScrapBook objects. (Use `wsb convert sb2wsb` and `wsb convert migrate` command of PyWebScrapBook to convert pages captured using legacy ScrapBook to WebScrapBook format.)

## [0.144.0] - 2021-11-21
* Added support of rewriting the `cite` attribute for several elements.
* Added support of handling the `ping` attribute for anchor elements, with a new option `capture.ping` to tweak the behavior.
* Resources used only by inline styles are no more counted as used when `Style images` is `Save used`.
* Added support of `%folder%` and `%path%` formatters for `Copy info` command of the sidebar.

## [0.143.0] - 2021-11-18
* Added support of capturing the source document embedded through an `<embed>` tag.
* Added support of handling legacy HTML attributes for a capture: `embed[pluginspage]`, `object[codebase]`, `object[archive]`, `object[classid]`, `applet[codebase]`, `applet[classid]`.
* Fixed an issue of message length error for Chromium if a page to be captured or saved exceeds around 50MB.
* Fixed an issue that `View source` in the current tab doesn't create new tabs when multiple items are selected.
* Fixed an issue that a link like "foo.html#?bar" is not shown in the sitemap.
* Fixed an issue that a frame page embedded through `<embed>` is not shown in the sitemap.
* Fixed an issue that a resource embedded through `<embed>`, `<object>`, or `<applet>` may not be blocked correctly in the viewer for Chromium.

## [0.142.0] - 2021-11-14
* Fixed an issue that a line of a rule for downloading links that is prefixed with spaces is not treated as a comment.
* No more take the link text as title (but available in the dropdown) when capturing a link for `Capture as` dialog.
* Allow the rule filler for in-depth capture be used for a capture with multiple tasks.
* Added `Same domain`, `Include with filter`, and `Exclude with filter` rule helpers for `Capture as` dialog.
* Fixed an issue that links covered by multiple selection ranges are duplicately included in a batch capture dialog.
* Fixed an issue that a failure to save the index file when saving as folder is not treated as a capture failure.
* Fixed an issue that a failure to save the file when saving as file is not treated as a capture failure.

## [0.141.0] - 2021-11-13
* Fixed an issue that an incorret option value is sometimes get when the options change.
* Added `Delay for capturing linked pages` option for the `Capture as` dialog.
* Added support of single click invocation of the toolbar button when only one command is shown.
* No more force all resources be data URL when an iframe with a data URL source is saved as srcdoc.
* Fixed an issue that the srcdoc attribute of a frame element is removed whan `Frames` option is `Blank`.
* Fixed an issue that the URL of a meta refresh is not correctly resolved when the page has a base element.
* Fixed incorrect source URL in the log message when there's an error during capturing a frame.
* The editor toolbar now appears at the top.
* Sticky notes now appear at the top, except for being under the editor toolbar.
* Implemented a more accurate server tree change detection algorithm to cover more possible cases.

## [0.140.0] - 2021-11-11
* Added modifiers support for toolbar commands.
* Added multi-tab support for `Batch capture selected links` toolbar command.
* Added drag-and-drop support for `Batch capture all tabs` and `Batch capture selected links` toolbar commands.
* Fixed an issue that sidebar fails to reload when data changes rapidly within a second.
* Fixed a siderbar styling issue for older Firefox.

## [0.139.0] - 2021-11-10
* Fixed an error of editing a created postit in Firefox.
* Fixed several UI issues for the sidebar.
* Adjusted scrollings for the item picker dialog.

## [0.138.0] - 2021-11-09
* Fixed an issue that a capture may be interrupted occasionally when saved to folder as folder.
* Minor UI improvements.

## [0.137.0] - 2021-11-07
* Added a capture helper command: `isolate`.
* Fixed incorrect title for `Capture frame as`.
* Improved the GUI of the target item selector for `Capture as` dialog.
* Added a rule filler for in-depth capture for `Capture as` dialog.
* No more include URLs with non-http(s) protocol for batch capture.
* Fixed an issue that the item picker for `Capture as` dialog incorrectly allows multi-selection through holding Shift.
* Various minor bug fixes and UI improvements.

## [0.136.0] - 2021-11-05
* Fixed several GUI issues for the `Capture as` dialog for a multi-item capture.

## [0.135.0] - 2021-11-04
* Fixed an issue that `Capture again` does not work correctly if `Save captured data to` is not `Backend server`.
* Added a link for the backuped page for re-capture if available. (Requires server >= 0.46)

## [0.134.0] - 2021-11-02
* Added support of `mime:` prefix to filter linked files by MIME type.
* Fixed an issue that a linked file with no Content-Type header is not correctly handled by the file type filter.
* Fixed an issue that a reloaded iframe has inconsistent editor status with the main frame.

## [0.133.0] - 2021-10-31
* A linked web page is no more downloaded as a resource file if `Depth to capture linked pages` is set.
* A linked attachment web page is now correctly treated as a resource file.
* Added `Extra URLs` option for the capture dialog.
* Fixed an issue that size limit does not work for a linked page with depth 1.
* Fixed an issue of capturing unexpected linked pages in a frame whose source is data protocol.
* Fixed an issue that a link in an extension tab cannot be opened in some browsers.

## [0.132.0] - 2021-10-29
* Improved GUI for the `Capture as` dialog.
* A configured option whose value is same as default now updates with the app.

## [0.131.0] - 2021-10-28
* Implemented new GUI for the `Capture as` dialog.
* Various bug fixes and minor UI improvements.

## [0.130.0] - 2021-10-23
* Fixed an issue that some resource files such as SVG be incorrectly included for links rebuilding.
* An error during links rebulding for a document no more terminates the capture task.
* Fixed missing meta attributes for the index.html when capturing a XHTML or SVG file.
* Pages other than index.html now records only source URL in meta attributes.
* Header content type now takes higher priority than filename when checking links for downloading.
* Added a new `capture.downLink.doc.mode` option for capturing linked pages using tab mode.
* Added `View sitemap` editor tool.
* Improved UI and tooltips for edit and postit dialog pages.

## [0.129.0] - 2021-10-22
* Added support of saving meta refreshed pages for in-depth capture.
* An automatically opened remote tab is now closed on error.
* An error on capturing a linked page no more terminates the capture task.
* Improved internal processing and log messages for remote tab and in-depth capture.
* `ui.notifyPageCaptured` now defaults to true.
* Require server address field be filled when a backend server related option is used.
* Improved UI and tooltips for the options dialog.

## [0.128.0] - 2021-10-19
* Added capture helper commands: `concat`, `slice`, `upper`, `lower`, `encode_uri`, `decode_uri`, `add`, `subtract`, `multiply`, `divide`, `mod`, and `power`.
* Reworked capture helper commands `attr`, `css`, and `options` to support the parameter pattern `[[name1, value1], [name2, value2], ...]`.
* Renamed capture helper commands `has_elem` to `has_node`.
* Reworked capture helper command `insert` to take JSON node data.
* Reworked capture helper commands `match` and `replace` to always return a string value.
* Reworked UI for the `Capture as` dialog as `Batch capture` and `Advanced capture` dialogs.
* Break words for option textareas.
* Improved some option tooltips.

## [0.127.0] - 2021-10-17
* Improved UI for the `Capture as` dialog.
* Improved some option tooltips.

## [0.126.0] - 2021-10-11
* Added a new `capture.faviconAttrs` option for saving favicon-like resources.
* Adjusted UI for the `Capture as` dialog.
* Added support of sidebar auto-rebuilding after a capture, with a new option `scrapbook.autoRebuildSidebars` to tweak the behavior..

## [0.125.7] - 2021-10-10
* Fixed an issue that downloading links not working in the archive page viewer.

## [0.125.6] - 2021-09-22
* Fixed a packing error.

## [0.125.5] - 2021-09-22
* Fixed capture error for a page with a link element without href attribute.

## [0.125.4] - 2021-09-21
* Fixed an issue that noscript content is not correctly saved when captured using Firefox.
* Fixed an issue that noscript content is not correctly saved when capturing source.
* Fixed an issue that noscript content becomes escaped after saved by the editor.

## [0.125.3] - 2021-09-21
* Fixed a compatibility issue for saved tree data with old browsers not supporting ES2019.

## [0.125.0] - 2021-06-29
* Added a new `viewer.viewAttachments` option to force opening attachments using the archive page viewer.

## [0.124.0] - 2021-06-09
* Added hotkeys for batch capture page.
* Fixed an issue that clicked links with specified target or base URL not working in the archive page viewer.

## [0.123.0] - 2021-06-06
* Fixed an issue that modified options not taken when invoking a capture in some ways.
* Imported options without saving are no more applied.
* Support auto-updating options for sidebar and more scrapbook-related pages.

## [0.122.0] - 2021-05-30
* Added support of depth > 0 for merge capture.
* Added `View source page` editor tool.
* Adjusted format of the `index.json` file generated by in-depth capture.
* Fixed an issue that the URL of a redirected or meta refreshed page is not correctly rewritten for in-depth capture.
* Fixed an issue that resources under file: protocol cannot be captured.
* Fixed an issue that some context menu commands don't work.

## [0.121.0] - 2021-05-26
* Added `Find previous/next annotation` editor tool.

## [0.120.0] - 2021-05-21
* Optimized code for internal cache for better performance.
* Adjusted schema for IndexedDB-related internal cache for better performance.

## [0.119.0] - 2021-05-14
* Added and adjusted several default highlighter style options.
* Adjusted default highlighter styles.
* Added support of `imagesrcset` attribute for `<link>`s.
* Added support of `rel` value `modulepreload`, `prerender`, `dns-prefetch`, or `preconnect` for `<link>` tags.
* Added a new `capture.prefetch` option to tweak handling of prefetch-like `<link>` tags.
* Added `capture.contentSecurityPolicy` option to tweak handling of `content-security-policy` meta tag and `nonce` attribute.
* Removed `capture.removeIntegrity` option.
* `crossorigin` attribute is now removed only when a resource is saved.
* `integrity` attribute is now removed only for related tags.

## [0.118.0] - 2021-05-08
* Added support of capturing the source document embedded through an `<object>` tag.
* No more save XHTML or SVG files as srcdoc when saving as single HTML.

## [0.117.0] - 2021-05-05
* Improved config checking of capture helpers and autocapture to prevent more possible bad input.
* Fixed an issue that unfetchable resources are not skipped during internalization.
* Fixed an error when internalizaing a single HTML item. Internalized resources are now saved as data URLs in such case.

## [0.116.0] - 2021-05-03
* Capture the original page rather than the meta refreshed target page if the meta refresh time is non-zero.
* Improved the tooltips about autosave.
* Adjusted handling of some HTTP headers and HTML attributes to conform with the spec better.
* Fixed some potential errors for ASCII whitespace handling.
* Fixed a potential error handling for nested svg and math elements.

## [0.115.0] - 2021-05-01
* Preloads and prefetches are now removed by default, with a new option `capture.preload` to tweak the behavior.
* Shadow DOMs are saved as `data-scrapbook-shadowdom` attribute in place of `data-scrapbook-shadowroot`, with simplified data structure and smaller size.

## [0.114.0] - 2021-04-27
* Hash part of source URL is now considered when viewing an item.
* Fixed an issue that URL hash is not included in the source URL for the captured item.
* Fixed several issues on handling an item whose index file is an archive.

## [0.113.0] - 2021-04-24
* Added support of more modes for `Form status` capture option.
* Added a default option for the backend server URL option.
* Added support of enabling/disabling undo feature from its context menu.
* Added support of `Home` and `End` for sidebar key navigation.
* Added a message for a scrapbook configured as `no_tree` in the sidebar.
* Added support of `limit:` command for search.
* Fixed an issue that certain interactive properties, such as form status, canvas, and shadow DOM, are lost after an unerase in a re-loaded document.
* Fixed an issue that unrelated content in the document be refreshed after an undo.
* Fixed an issue that certain interactive properties, such as canvas and shadow DOM, are lost after an undo.
* Fixed missing support of opening in new tab for `View index page` sidebar command.
* Fixed an issue that the opened postit is not saved when switching scrapbook.
* Fixed an issue that switching scrapbook after a change of server config can load incorrect tree data.
* Fixed an error causing the copy item dialog in a manage dialog not working.
* Fixed an error causing unit tests not working.

## [0.112.0] - 2021-04-19
* Added options for whether to open in new tab for sidebar operations. Most operations now defaults to open in the active tab.
* Added support of opening in new tab by holding Ctrl or Shift for sidebar operations.
* Added support of adding as child item by holding Alt when creating a new item in the sidebar.
* Added support of recursive copy info by holding Ctrl or Shift.
* Allow opening multiple search tabs from the sidebar.
* Fixed an issue of missing `index` key when invoking `capture as` through dragging and dropping.
* Fixed an error when invoking copy info with an item having a malformed source URL.

## [0.111.0] - 2021-04-17
* Improved GUI for batch capture dialog.
* Added support of captured pages notification for captures during the same browser session.
* Moved option `scrapbook.notifyPageCaptured` to `ui.notifyPageCaptured`.
* Notification of captured pages now updates when a capture succeeds.
* Reworked duplicates detection for autocapture to check for captures during the same browser session and items in the backend server.
* Fixed an issue of script error for Firefox for Android < 55.

## [0.110.0] - 2021-04-14
* Fixed a regression that saved filename for a capture does not have `/`s generated by a placeholder tidied.

## [0.109.0] - 2021-04-11
* Added support of context displaying for the search page.
* No more save a file named `history.rdf`, which is preserved by MAFF format, when capturing a page.
* Fixed an issue of occasional unexpected extending of highlight range for the page editor.
* Fixed an issue that a text crop may cut between a unicode surrogate pair.

## [0.108.0] - 2021-04-05
* Improved GUI for options verification.
* Reworked the syntax of `capture.saveFilename` option.
* Added support of auto-capture in the options.
* Added `copyinfo` command to sidebar.

## [0.107.0] - 2021-04-03
* Added support of viewing folder items.
* Added support of editing a postit in the sidebar.
* Added support of `tc:`, `charset:`, and `location:` search commands.
* Improved GUI for note and postit editors.
* Fixed several compatibility issues in Firefox 52.

## [0.106.0] - 2021-04-01
* Bumped server requirement to >= 0.36.
* Added support of note for a backup.
* Automatically create a tree backup for each transaction to prevent an accidental file corruption, with a new option `scrapbook.transactionAutoBackup` to tweak the behavior.

## [0.105.0] - 2021-03-28
* Fixed an issue that nothing is captured when selecting exactly a single node.
* Fixed an issue that nodes outside the html node are not captured.
* Improved capture selection to support more special cases, such as a selection outside of the body node.
* No more generate linefeeds for the capture/save content by default, with a new option `capture.preffyPrint` to tweak the behavior.
* Added `attach link` to the editor tools.

## [0.104.1] - 2021-03-27
* Fixed an issue that special chars (e.g. `<`, `&`, and `>`) in a postit item are not loaded correctly.

## [0.104.0] - 2021-03-27
* WebScrapBook loaders are now injected as last elements in `<body>` rather than after `<body>`.
* No more create loaders for non-annotated highlights.

## [0.102.0] - 2021-03-16
* Added support of copying item IDs of the tree selection via Ctrl+C.
* Fulltext cache is now updated automatically only when `Generate fulltext cache` option is checked.

## [0.101.0] - 2021-03-08
* Added support of capturing via dragging a browser action command into the sidebar.

## [0.100.0] - 2021-03-01
* Added support of geolocation metadata.

## [0.98.0] - 2021-01-24
* Reworked option `capture.requestReferrer` as `capture.referrerPolicy`, which supports options as the `Referrer-Policy` HTTP header.
* Added option `capture.referrerSpoofSource`.

## [0.97.0] - 2021-01-03
* Added support of post-it items.

## [0.95.0] - 2020-11-18
* Changed internal identifier for auto-close dialog option.
* Added support of `Capture as`.

## [0.93.0] - 2020-11-13
* Added a capture option `Save resources sequentially`.
* Reworked auto-close dialog option to support more modes.

## [0.92.0] - 2020-11-11
* Added support of in-depth capture.
* Changed internal identifier for some capture links (download linked files) related options.

## [0.89.0] - 2020-10-31
* Added `Copy` command to sidebar.
* Added support for cross-scrapbook drag-and-drop.
* The descendant items are now automatically deselected when an item is toggled collapsed.
* Fixed an issue that the sidebar is unlocked when a dialog is dismissed, even though the command is still running.

## [0.88.0] - 2020-10-29
* Added support of editing created and modified time in the sidebar.
* Added support of `index:` command for the search page.

## [0.87.0] - 2020-10-27
* Bumped server requirement to >= 0.29.
* Added `Sort` command to sidebar.
* Added `Capture again` command to sidebar.

## [0.86.0] - 2020-10-26
* Fixed styling error for `site` and `combine` types.

## [0.85.0] - 2020-10-25
* Added an option `Show hint when browsing a page having been captured` and a toolbar command `View captured pages`.

## [0.84.0] - 2020-10-22
* Reworked `Batch capture` as `Batch capture all tabs`, and remove `Capture all tabs`.
* Fixed an issue that backup files are generated for auto fulltext cache.

## [0.83.0] - 2020-10-19
* Changed view status caching format for sidebar to avoid a comflict within different views.
* Added support of top-level null value for *.js tree files.

## [0.82.0] - 2020-10-17
* Added a capture option to specify delay time before capturing an auto-launching tab.
* Added a capture option to insert an infobar.
* Improved capture helpers:
  * Added `name` and `debug` properties.
  * Added `options` and `insert` commands.
  * Added support to debug a capture helper commands using `*` prefix.
  * Improved error reporting.
* Improved sidebar and manage dialog:
  * Adjusted command button to show scrapbook-related commands rather than echo the context menu.
  * Added `Search within` command to sidebar.
  * Added `Recover` command for a recycle bin to sidebar.

## [0.81.0] - 2020-10-14
* Reworked editor toolbar:
  * Added context menu in place of sub-menu buttons. This prevents toolbar overflow on mobile browsers.
  * Enlarged toolbar and buttons.

## [0.79.0] - 2020-10-06
* Bumped server requirement to >= 0.23.
* Reworked site indexer:
  * Moved site indexer button from browser action to options page.
  * Shifted site indexer to server-side, with greatly improved performance, and minor format change. (Consider recreate fulltext cache.)
  * Automatically update fulltext cache when a web page or note is captured or edited.
  * Added data checker. Moved the feature of importing non-indexed web page files through site indexer to data checker.
  * Dropped support of site indexing through dragging and dropping local filesystem folders or ZIP files.
  * Dropped support of importing legacy ScrapBook data through site indexer. (Use `wsb convert sb2wsb` of PyWebScrapBook instead.)
* Added `disabled` capture helper property.

## [0.78.0] - 2020-09-20
* Added `Accept` header for requests to the backend server. This allows the reverse proxy server or upper server to response with a more appropriate format to the client.

## [0.76.0] - 2020-09-06
* Added support of self version checking. An error will now be thrown if the extension version is too old to work with the corresponding backend server.
* A request for acquiring an access token now uses a POST rather than GET method.

## [0.75.6] - 2020-09-05
* Bumped server requirement to >= 0.17.

## [0.75.0] - 2020-05-25
* Merged record related capture options.

## [0.73.0] - 2020-05-08
* Added support of GUI editor of annotated marker for page editor.

## [0.70.0] - 2020-04-27
* Added support of annotated marker for page editor.
* Added support of sticky note for page editor.

## [0.68.0] - 2020-04-17
* Dropped support of using filesystem API for viewing a page archive.

## [0.63.0] - 2020-04-04
* Added search and edit to the sidebar.

## [0.62.0] - 2020-03-22
* Added capture helper, in place of the preclude option.

## [0.60.0] - 2020-01-25
* Bumped server requirement to >= 0.12.
* Implemented new transferring protocol to improve the performance of indexing through the backend server.

## [0.59.0] - 2020-01-18
* Added support of context menu for the sidebar.

## [0.53.0] - 2019-09-27
* Added a capture option to remove hidden elements.
* Added a capture option to preclude elements.
* Added a capture option to limit resource size to download.

## [0.52.0] - 2019-09-15
* Dropped support of `Scripted single HTML` format for a page capture.

## [0.51.0] - 2019-09-13
* Added support to capture shadowRoot content.

## [0.50.0] - 2019-09-08
* Fixed an issue that page editor is loaded for every page if backend server URL is not set.

## [0.49.0] - 2019-09-07
* Added page editor.

## [0.48.0] - 2019-09-01
* Bumped server requirement to >= 0.8.
* Added support for `no_tree` scrapbooks.

## [0.46.0] - 2019-08-25
* Added support of drag and drop to manage scrapbook items.

## [0.45.0] - 2019-07-01
* Added support to capture dynamic CSS.

## [0.44.1] - 2019-05-30
* Fixed a packaging error for 0.44.0.

## [0.41.0] - 2019-04-15
* Bumped server requirement to >= 0.6.
* Now use `save` instead of `upload` action to upload a file.

## [0.39.2] - 2019-03-31
* Bumped server requirement to >= 0.3.

## [0.37.0] - 2019-03-18
* Bumped server requirement to >= 0.2.
* Added support of backend server version checking. An error will now be thrown if the backend server version is too old to work with this extension.

## [0.36.0] - 2019-03-14
* Added support for sidebar and backend server.

## [0.32.0] - 2019-02-23
* Dropped support of Firefox < 52 and Chromium < 55.
* Refactor the code to work with async function.

## [0.27.0] - 2018-08-25
* Dropped support of JavaScript when viewing a page archive, due to a security concern.

## [0.25.0] - 2017-12-29
* Added unit tests.

## [0.17.0] - 2017-11-15
* Added site indexer.

## [0.1.0] - 2017-07-11
* First public release.
