# Global-iExitLoop-0-hGUIParent1-hGUIParent2-iLoadGuiTwo-0-Example1-Example2-not-a
Global $iExitLoop = 0, $hGUIParent1, $hGUIParent2, $iLoadGuiTwo = 0 Example1() ;~ Example2() ; not an example but a GUI ? Func Example1($iParent = 0)     Opt("GUIOnEventMode", 1)     $hGUIParent1 = GUICreate("Parent", 400, 300, -1, -1, -1, -1, $iParent)     GUISetOnEvent($GUI_EVENT_CLOSE, "OnEvent_CLOSE_ONE", $hGUIParent1)     GUICtrlCreateButton("load GUI TWO", 8, 8, 100)     GUICtrlSetOnEvent(-1, "LoadGuiTwoFromGuiOne")     GUISetState(@SW_SHOW)      While 1 ; Loop until the user exits.         Sleep(100) ;~      If $iLoadGuiTwo Then ; .......... solution 1 ;~          Example2($hGUIParent1) ; .... ;~          $iLoadGuiTwo = 0 ; .......... ;~      EndIf ; .........................         If $iExitLoop Then ExitLoop     WEnd     $iExitLoop = 0     GUIDelete($hGUIParent1) EndFunc   ;==>Example1
