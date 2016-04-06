# Introduction #

![http://iphone-patch.googlecode.com/files/bgkeyboard-0.1-1.jpg](http://iphone-patch.googlecode.com/files/bgkeyboard-0.1-1.jpg)

**Bulgarian Phonetic Keyboard** for FW 2.0 is a hack against the TextInput\_ru bundle with the popular Bulgarian Phonetic Layout. Please remember that this is work in progress and some features might not work as expected. Reporting bugs/ideas is welcome.

# Features #
  * Phonetic Layout
  * Light and dark horizontal and vertical keyboards.

# TODO #
  * BDS Layout.
  * Bulgarian auto-correction dictionary.

# Changes #
  * **1.0** - Seems stable, no bugs reported, should work with 2.0.2
  * **0.3** - Almost nothing new, works with 2.0.1
  * **0.2** - Transparent images fixed.
  * **0.1** - Initial version. Horizontal and vertical light keyboards are working, installs and uninstalls fine.

# Download and Installation #

You can install the package in the following ways:
  * Install **"iPhone Patch's Source"** From **"Repositories"** section in Cydia (recommended).
  * Add `deb http://mspasov.com/ stable main` to your `sources.list` file.
  * Download the last version from the Downloads tab and install it by hand.

# Donations #

If you like the work done here, please check the [Donations](Donations.md) page. Thank you!

# Details #

The package itself replaces the TextInput\_ru.bundle with modified files. Here are the steps that I used, developing the package:

  * Used IDA to disassemble the binary.
  * After some looking found `\0\0` terminated 4 byte unicode characters.
  * I have mapped the positions and did some hex editing
  * Found out that artwork should be edited. No utility supporting Text\_Bundle\_ru was available, so hunt for offsets and sizes began..
  * Modified one .py script to extract and assemble the artwork.
  * Edited the keyboard images with Gimp:
    * Removing the letters from the background.
    * Creating layouts for Russian and BG Phonetic keyboard (I'll publish XCF files soon).
  * Assembled the modified .artwork
  * Resigned the modified binary
  * Created the debian package.

All this was done in two days.