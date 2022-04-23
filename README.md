# ClipPut
#include &lt;Misc.au3>  ; Version: 1.00. AutoIt: V3.3.8.1 ; Retrieve the recommended information of the current system when posting a support question. Local $sSystemInfo = 'I have a valid AutoIt support question and kindly provide the details of my system:' &amp; @CRLF &amp; @CRLF &amp; _         'AutoIt Version: V' &amp; @AutoItVersion &amp; ' [' &amp; _Iif(@AutoItX64, 'X64', 'X32') &amp; ']' &amp; @CRLF &amp; _         'Windows Version: ' &amp; @OSVersion &amp; ' [' &amp; _GetOSLanguage() &amp; ']' &amp; @CRLF &amp; _         'Language: ' &amp; @OSLang &amp; @CRLF &amp; @CRLF MsgBox(4096, 'This info has been copied to the clipboard. Use Ctrl + V to retrieve it.', $sSystemInfo) ClipPut($sSystemInfo)  ; #FUNCTION# ==================================================================================================================== ; Name ..........: _GetOSLanguage ; Description ...: Retrieves the language of the OS, this supports 19 of the most popular languages. ; Syntax ........: _GetOSLanguage() ; Parameters ....: None ; Return values .: None ; Author ........: guinness ; Link ..........: http://www.autoitscript.com/forum/topic/131832-getoslanguage-retrieve-the-language-of-the-os/ ; Example .......: No ; =============================================================================================================================== Func _GetOSLanguage()     Local $aString[20] = [19, "0409 0809 0c09 1009 1409 1809 1c09 2009 2409 2809 2c09 3009 3409", "0404 0804 0c04 1004 0406", "0406", "0413 0813", "0425", _             "040b", "040c 080c 0c0c 100c 140c 180c", "0407 0807 0c07 1007 1407", "040e", "0410 0810", _             "0411", "0414 0814", "0415", "0416 0816", "0418", _             "0419", "081a 0c1a", "040a 080a 0c0a 100a 140a 180a 1c0a 200a 240a 280a 2c0a 300a 340a 380a 3c0a 400a 440a 480a 4c0a 500a", "041d 081d"]      Local $aLanguage[20] = [19, "English", "Chinese", "Danish", "Dutch", "Estonian", "Finnish", "French", "German", "Hungarian", "Italian", _             "Japanese", "Norwegian", "Polish", "Portuguese", "Romanian", "Russian", "Serbian", "Spanish", "Swedish"]     For $i = 1 To $aString[0]         If StringInStr($aString[$i], @OSLang) Then             Return $aLanguage[$i]         EndIf     Next     Return $aLanguage[1] EndFunc   ;==>_GetOSLanguage
