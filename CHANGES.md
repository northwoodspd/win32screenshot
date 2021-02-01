# 3.0.1 2021-02-01
*   Updated gems
*   Fixed deprecations around rspec syntax (`should` is now `expect`)

# 3.0.0 2019-12-11
*   Use RAutomation 1.0.0 as its dependency to be able to use newer ffi.
*   Update bundled ImageMagick to 7.0.9-8.
*   Update MiniMagick dependency.

# 2.1.0 2016-01-09
*   Add Image#write! for overwriting images.
*   Update MiniMagick dependency.
*   Update bundled ImageMagick version to 6.9.3-0-portable-Q16-x86.


# 2.0.0 2015-06-28
*   Update MiniMagick dependency due to CVE-2013-2616.
*   Update bundled ImageMagick version to 6.9.1-6-Q16-x86.


# 1.0.10 2013-11-01
*   Add license to gemspec.


# 1.0.9 2013-10-05
*   Set mini_magick 3.5.0 as a dependency because 3.6.0 is broken.


# 1.0.8 2013-03-09
*   Loosen up dependencies


# 1.0.7 2012-02-23
*   Bump RAutomation dependency


# 1.0.6 2011-10-16
*   Screenshot will be taken of the whole window instead of client area - e.g.
    with title bar and such.
*   Added :context option to specify which area to take screenshot of -
    possible values are :window or :client
        Win32::Screenshot::Take.of(:window, :hwnd => 1234, :context => :client)


# 1.0.5 2011-08-18
*   Minor output message change


# 1.0.4 2011-06-18
*   Make sure that mini_magick 3.2 is used due to bug in 3.3-s dependency
    subexec https://github.com/nulayer/subexec/issues/4


# 1.0.3 2011-04-17
*   Try to take a screenshot of the window even if the activation of that
    window fails.


# 1.0.2 2011-01-20
*   Fixed to work with RAutomation version 0.4


# 1.0.1 2010-12-18
*   Increased RAutomation dependency for version 0.3.0 due to it's new
    Window#child method
*   Making sure that RAutomation's Ffi adapter is always used


# 1.0.0 2010-12-17 - The New Beginning
*   Bundling all necessary libraries/binaries with the gem - ImageMagick and
    RMagick are no more needed, finally!
*   Using MiniMagick to save images to gif, jpg and png format
*   Simplified and deleted a lot of code causing backwards incompatibility and
    major API changes!
        Refer to the README.rdoc and documentation for the overview of the new and better API

*   From now on this library is following Semantic Versioning
    (http://semver.org) rules


# 0.0.8 2010-12-13
*   Renamed Win32::Screenshot::Util.all_windows to all_desktop_windows (Roger
    Pack)
*   Added methods to Win32::Screenshot::Util class (Roger Pack):
    *   window_process_id
    *   window_class
    *   windows_hierarchy_with_info
    *   get_info
    *   location_of

*   It's possible to search windows also by class name (Roger Pack)
*   Child windows will be also searched for (Roger Pack)


# 0.0.7 2010-08-18
*   Supports now fully JRuby, 1.9.1 and 1.9.2 MRI!


# 0.0.6 2010-08-07
*   Trying to bring window to the foreground more aggressively (Roger Pack)
*   Added utility class Win32::Screenshot.Util with some helper methods not
    related directly with taking of the screenshots:
    *   all_windows - enumerates all windows and returns their titles and
        window handles as an Array (Roger Pack)
    *   window_title(hwnd) - returns title of the window for specified handle
        (Jarmo Pertman)
    *   window_hwnd(title_query) - returns handle of the window for specified
        title (Jarmo Pertman)
    *   dimensions_for(hwnd) - returns a width and height for a window with
        specified handle (Jarmo Pertman)

*   Removed a file 'win32screenshot.rb' which was solely used for displaying
    deprecation warnings for versions older than 0.0.4. Make sure than from
    now on all require statements require 'win32/screenshot'!


## Bug Fixes:
*   Fixed usages of gdi32.dll BitBlt (Roger Pack)
*   It was impossible to specify correctly window titles with regular
    expressions special characters in them (Roger Pack)


# 0.0.5 2010-07-07
*   Added method window_area for capturing specified area of the window
    instead of full window (Jarmo Pertman) Usage:
    Win32::Screenshot.window_area(title, x1, y1, x2, y2) {|width, height,
    bmp|}
*   Added method foreground_area for capturing area of the foreground (Jarmo
    Pertman) Usage: Win32::Screenshot.foreground_area(x1, y1, x2, y2) {|width,
    height, bmp|}
*   Added method desktop_area for capturing area of the visible view (Jarmo
    Pertman) Usage: Win32::Screenshot.desktop_area(x1, y1, x2, y2) {|width,
    height, bmp|}
*   Added method hwnd_area for capturing area of the window with specified
    handle (Jarmo Pertman) Usage: Win32::Screenshot.hwnd_area(hwnd, x1, y1,
    x2, y2) {|width, height, bmp|}


## Internal changes
*   Removed usage of ShowWindow with parameter SW_SHOW when trying to bring
    window to front due it's behaviour of resizing window if it was maximized
    (Jarmo Pertman)
*   Using FFI::Struct when searching window handle (Roger Pack)


# 0.0.4 2010-05-27 - A Complete Overhaul
*   Fixed a bug where taking of screenshots failed on some sizes of windows
    (thanks for the tip from Tony Popiel)
*   Blocks should be used when taking screenshots for cleaning up resources
    after usage (Aslak Hellesøy)
*   Changed library structure - it is now needed to require 'win32/screenshot'
    (Aslak Hellesøy)
*   Replaced Ruby::DL with Ruby-FFI for better VM support and less segfaults
    (Jarmo Pertman)
*   Added Ruby 1.9.1 support (Jarmo Pertman)
*   Win32::Screenshot.window restores window if it's minimized before taking
    screenshots and brings it to the foreground (Jarmo Pertman)
*   Changed some internal method names (Jarmo Pertman)
*   Replaced Test::Unit with RSpec and made specs more robust (Jarmo Pertman)


PS! This version is not backwards compatible due to different method names and
usage, but upgrading should be relatively easy nevertheless.

# 0.0.3 2007-01-18
*   Fixed bug with too many callbacks
*   Added get_hwnd(Regexp)


# 0.0.2 2006-12-02 
*   Added desktop method (patch from Ryan Schuft)
*   Added HTTP server example (patch from Ryan Schuft)
*   Added window(regexp) method


# 0.0.1 2006-11-29
*   First release

