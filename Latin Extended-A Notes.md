
Latin Extended-A Notes
----------------------

I neither read nor write any of the languages that use Latin Extended-A glyphs, so I have designed these glyphs using other Sans Serif fonts as reference.

Here is a list of the glyphs in the Latin Extended-A Code Block: 

http://unicode.org/charts/PDF/U0100.pdf


Manual Additions:
-----------------

All manual additions added in robofont or through editing the UFO files by hand.

Notes:
 * To compose dcaron (0x010F), lcaron (0x013E) and Lcaron (0x013D), I used quotesingle and horizontal spacing of 0.050em (50 font measurement units).  
   There was no existing precedent for this spacing in the font, and it seemed to make sense visually to make this spacing 
   slightly tighter than the 0.065 em used for vertically spacing diacriticals.
 * To compose Ldot (0x013F) and ldot (0x0140), I used middle dot (0x00B7) without altering its vertical position.  
   I again used 0.050 em horizontal spacing for ldot (see above), but for Ldot I used less so that the dot would not exceed the right edge of the foot of the L.
   This tighter spacing of 0.038 em looks too tight, but I deemed the alternatives (lengthening the foot of the L or having the dot exceed the foot's edge) worse.
 * Dcroat is just a copy of Eth.
 * dcroat, Hbar and hbar crossbars are modeled after the t crossbar.
 * Generally, I updated the right side-bearings if necessary to remain consistent (0.040em).
 * To compose the ij ligature, I used the same horizontal spacing (0.074em) as the fi ligature.  The IJ ligature uses less for optical reasons.
 * I composed the napostrophe (0x0149 Latin Small Letter N Preceded by Apostrophe) from n and a single quote.  
   The spacing is very tight in other fonts so I followed that convention.
 * Likewise, the spacing is very tight in tcaron (0x0165).
 * I composed the Eng (0x014A) from N and J.  I slightly modified the tail from J by 5 pixels.
 * The crossbar of the Tbar (0x0166) and tbar (0x0167) is modeled on the crossbar from f.  
   The crossbar of tbar is quite controversial.  Popular fonts display a wide variety of styles.  I attempted to arrive at a happy compromise.
 * I composed from longs (0x017F) from the f by removing the right side of the crossbar.  This is conventional.
 * I composed the kgreenlandic (0x0138) Latin Small Letter Kra by vertically scaling down the K to the x-height.  This may not be ideal.


Automated additions:
--------------------

All automated additions added using font-interpolator, a set of python scripts I wrote for this purpose.

It is available here: https://github.com/charlesmchen/font-interpolator
 
Notes:

 * Spacing between base glyphs and diacriticals is 0.065 em, ie. 65 font measurement units which exactly matches existing diacriticals in the font.
 * Generally, diacriticals horizontally centered on base glyphs but with a large number of exceptions.

font-interpolator was invoked with the following configuration:

font-interpolator --ufo-src=/Users/charleschen/code/workspace/font-interpolator/data-ignore/League Gothic.modified.ufo --ufo-dst=/Users/charleschen/code/workspace/font-interpolator/out/League Gothic.ufo --log-dst=/Users/charleschen/code/workspace/font-interpolator/logs --top-join-centers 0x60 261 0xB4 239 0x6A 87.5 0x4A 118 0x67 157 0x47 177 0x2DD 218 0x52 148 0x72 130 0x74 111.5 0x4C 94.0 0x44 175.0 0x64 140.0 --tail-join-centers 0xAF 260.0 0x41 311.5,0 0x61 253.0,0 0x45 230,0 0x65 162,0


Other Notes:
------------

 * The Latin Extended-A Code Block is now complete.
 * Robofont is based on robofab.  Robofab's validation issues "ignoring empty contour segment" warnings for many glyphs.
 * I've cleaned up small errors in the original font:
   * An erroneous bezier in the H.
   * The font used many unnecessary bezier curves to represent straight lines.  
     I've culled them using rf-contour-cleanup, a robofont extension I wrote for this purpose.  
     It is available here: https://github.com/charlesmchen/robofont-extensions-and-scripts
 * Robofont and FontLab apparently use different naming syntax for the glyph groups.  Therefore I haven't preserved/updated the groups properly.
 * There are various compound glyphs which can be composed using more than one diacritical.  
   For example, ncedilla (0x0146) and Ncedilla (0x0145) can be composed with a traditional "curved tail" cedilla or with a "comma accent".
   The "comma accent" form is much more common in popular fonts, so I followed that convention.
   Likewise, wherever there was inconsistency with other compound glyphs I followed the convention.

    
Kerning:
--------

 * I haven't done any kerning.
 * The following glyphs could really use it:
   * tcaron (0x0165)
   * tcommaaccent (0x0163)
   * Ldot
   * ldot
   * Lcaron
   * lcaron
   * hbar
   * Hbar
   * napostrophe
   * Dcroat
   * dcaron
   
   
   
