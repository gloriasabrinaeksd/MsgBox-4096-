# MsgBox-4096-
Local $iSingleton = _SingletonPID('RandomName', 1)  If $iSingleton = 0 Then     MsgBox(4096, '', 'This is the first instance of the program running: ' &amp; $iSingleton) Else     MsgBox(4096, '', 'There is another instance running. This PID is: ' &amp; $iSingleton)      ; Wait for the process to close.     ProcessWaitClose($iSingleton, 5)      ; Reset _SingletonPID to current process since the previous one was closed.     $iSingleton = _SingletonPID('RandomName', 1)     MsgBox(4096, '', 'This is now the first instance of the program running: ' &amp; $iSingleton) EndIf
