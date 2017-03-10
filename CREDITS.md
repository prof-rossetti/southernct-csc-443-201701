# Credits, Notes, and Reference

  + [HTML Beautification Tool](http://www.cleancss.com/html-beautify/)
  + The demo Weather Widget / Single-page App was made by Google.
  + https://www.datavizforall.org/find/ct/

## Screencasting

  + [Converting QuickTime screen recordings to GIF format](https://gist.github.com/dergachev/4627207)): `ffmpeg -i ~/Dropbox/Screenshares/interactive-dataviz.mov -pix_fmt rgb24 -r 10 -f gif - | gifsicle --optimize=3 --delay=3 > projects/interactive-dataviz/demo.gif`
  + [Hiding all Folders on the Desktop](http://www.cultofmac.com/272595/quickly-hide-icons-desktop-os-x-tips/): `defaults write com.apple.finder CreateDesktop false && killall Finder`
  + Recording a screencast with audio (ALMOST, BUT NOT FULLY WORKING):
    + http://apple.stackexchange.com/a/213305/94120
    + https://www.cnet.com/how-to/record-your-computers-screen-with-audio-on-a-mac/
    + https://github.com/mattingalls/Soundflower/releases/tag/2.0b2
