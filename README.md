# Background
#include &lt;GDIPlus.au3> #include "GuiFlatButton.au3"  Example()  ;buttons with Icon images Func Example()      ;get images for demonstration     _GDIPlus_Startup() ;initialize GDI+     Local $hIcon = _WinAPI_ShellExtractIcon(@SystemDir &amp; '\shell32.dll', 258, 24, 24)   ;extract the 'Save' icon     Local $hBitmap = _GDIPlus_BitmapCreateFromHICON($hIcon)                             ;Create Bitmap from Icon (for demonstration)     Local $hHBitmap = _GDIPlus_BitmapCreateHBITMAPFromBitmap($hBitmap)                  ;Create HBitmap from Bitmap     _GDIPlus_BitmapDispose($hBitmap)                                                    ;dispose the bitmap     _GDIPlus_Shutdown() ;done with GDI+      Local $hGUI = GUICreate("GuiFlatButton Ex5", 255, 400)     GUISetBkColor(0xEEEEEE)      ;set default colors of future buttons     Local $aColorsEx = _     [0xE2E5E8, 0X000000, 0x888888, _    ; normal    : Background, Text, Border      0xE2E5E8, 0X000000, 0x333333, _    ; focus     : Background, Text, Border      0xE8E8E8, 0X000000, 0x666666, _    ; hover     : Background, Text, Border      0xDDDDDD, 0X000000, 0xAAAAAA]      ; selected  : Background, Text, Border     GuiFlatButton_SetDefaultColorsEx($aColorsEx)
