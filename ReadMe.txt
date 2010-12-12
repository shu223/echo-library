
CIColorTracking is an Objective-C applicaton that implements a GPU-based technique to 
find  the location of a uniquely colored object in a scene  and  then uses the position information 
to apply video effects.

AppController.h and AppController.m
These files contain a declaration and impelmentation of the AppController class. This class is a 
subclass of NSObject that allows you to control the user interface. The user interface allows the 
user to  to select a source movie, change tracking options, view the tracking video, see a preview 
of the mask used for the video, and overlay the mask image onto the tracking video.

VideoCIView.h and VideoCIView.m
These contain the declaration and implementation for the VideoCIView class which is a subclass of the
NSOpenGLView class. VideoCIView sets up and manages the OpenGL context that shows the video.

VideoHandler.h and VideoHandler.m
These files contain a declaration and impelmentation of the Viewhandler class, which is a subclass
of NSObject. VideoHandler sets up a Core Video display link and manages the display and context for
the tracking video (which is a QuickTime movie).

TrackingImageUnit is a self-contained project that creates an Image Unit. An image unit is a 
Core Image filter that is packaged as an NSBundle object. Filters  packaged as an image unit are
easy to distribute and use with other applications. This image unit is used by the CIColorTracking
project, but you can just as easily use the filters in TrackingImageUnit in any Mac OS X application
by copying the image unit to /Library/Graphics/Image Units. For more information on creating and
using Image Units and Core Image filters, got to http://developer.apple.com/ and search for
"Image Unit Tutorial" and "Core Image Programming Guide".

TrackingFilters.h and TrackingFilters.m
These files are in the TrackingImageUnit folder and contain the declaration and implementation for 
the TrackingFiltersPlugInLoader class, which takes care of registring the filters contained in these
files. These files also contain the declaraion and implementation for these CIFilter subclasses: 
CompositeFilter, Centeroid, CoordinateMaskWithColor, MaskFromColor, and GPUGemsAreaMean.

SYSTEM REQUIREMENTS:

Mac OS X v10.4 or later
Macintosh with G5 or Intel processor.

BUILD REQUIREMENTS:
Xcode version 2.3 
Interface Builder version 2.5

RUNNING THE APPLICATION:
1. Launch the application.
2. Select the movie that you want to use for tracking. 
3. Click  the Tracking Color well and pick the color  that you want to track. Use the loupe to pick color.
4. Set the Tolerance slider, so that the entire object that you want to track is visible in the Mask Preview. 
5. Play the movie by clicking Play/Pause button in the lower right corner. 
6. Turn on Show Composite in Viewer to see the duck on top of the tracked color object. 
You  see a live preview of the mask in the preview or you can overlay the mask in the main view by setting the opacity of the Overlay Mask.
