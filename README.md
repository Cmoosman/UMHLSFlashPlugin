UMHLSFlashPlugin
================

REQUIREMENTS
1.  Existing OSMF player built on version 1.6 or 2.0 of the OSMF framework           
2.	HLS Plugin for OSMF package acquired from Unicorn Media Client Services (UM-HLS-Package.zip)
a.	The package includes supported and non-supported reference sample elements:
Supported
i.	M3U8plugin.swf – required 
ii.	Playerglobal.swc – required for FlashBuilder setup

Not-Supported (Reference Sample Code Only)
i.	\CSS - Contains 2 sample style sheets to support the test page layout
ii.	\Images - Contains the header logo
iii.	\JS - Contains 4 java script files that support the test page layout and functionality
iv.	Index.htm - Basic implementation of a Strobe (OSMF player) media player loading the M3U8Plugin to provide a real life example for your reference
v.	StrobeMediaPlayback.swf - OSMF Flash video player V2.0 (OSMF framework)

Base Once URL Construct
For proper Once™ URL construction, refer to this URL template: prerequisite
once.unicornmedia.com/now/adaptive/m3u8/DomainGUID/ApplicationGUID/MediaItemGUID/content.m3u8?AdParams&Params
NOTE: The plugin responds only to an .m3u8 file extension.


IMPLEMENTATION
1.	Load the plugin on the flashvars as in the examples below: 
a.	Javascript - flashvars:{plugin_M3U8Plugin: 'M3U8Plugin.swf'} 
b.	HTML Object tag - <paramname="flashvars"value="plugin_M3U8Plugin= M3U8Plugin.swf">
NOTE: Do Not Rename the Plugin. You can upload it to a CDN or move it to an external webserver, but the file name MUST remain M3U8Plugin.swf

2.	Set the SRC property on the flashvars to the M3U8 URL:
a.	Javascript - flashvars: {src:‘http://once.unicornmedia.com/now/adaptive/m3u8/bef3c9b-9d80-4efd-b4ad-769509b/b1ef9b-9d80-4eaa-b4cc-769e309b/24340c-8dae-435e-d917-642c7/carscene/content.m3u8’,plugin_M3U8Plugin: 'M3U8Plugin.swf'} 
b.	HTML Object tag – 
<param name="flashvars"value="src=http://once.unicornmedia.com /now/adaptive/m3u8/bef3c9b-9d80-4efd-b4ad-769509b/b1ef9b-9d80-4eaa-b4cc-769e 309b/24340c-8dae-435e-d917-A642c7/carscene/cont ent.m3u8&plugin_M3U8Plugin= M3U8Plugin.swf">
Additional OnceVOD Parameter Option
You also have the option to force or temporarily override the Profile GUID(s) for adaptive playback by using umoprofiles={profileGUID}, {profileGUID}… as in this example.
http://once.unicornmedia.com/now/adaptive/m3u8/ bef3c9b-9d80-4efd-b4ad-769509b/b1ef9b-9d80-4eaa-b4cc-769e309b/24340c-8dae-435e-d917-a642c7/carscene/content.m3u8?umoprofiles=3a41c6e4-93a3-4108-8995-64ffca7b9106"

FlashBuilder Setup
1.	Create a new FlashBuilder project
2.	Use the 4.0 or newer Framework targeting the 10.1 Flash Player in the project ActionScript Compiler Settings dialog
a.	The swc file contained in the HLS Plugin for OSMF package (UM-HLS-Package.zip) must be placed in the Adobe Flash Builder directory 
b.	Example of default directory placement: C:\Program Files (x86)\Adobe\Adobe Flash Builder 4\sdks\4.6.0\frameworks\libs\player\10.1\playerglobal.swc

