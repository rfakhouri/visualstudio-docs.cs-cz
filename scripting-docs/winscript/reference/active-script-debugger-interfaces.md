---
title: Rozhraní ladicího programu aktivních skriptů | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Active Script Debugger interfaces
- activdbg.h
ms.assetid: bf4750b1-4e58-442b-ab56-254e640de61d
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d4a3d17a8ff43bb3bd18641c2298f5436f40d925
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792348"
---
# <a name="active-script-debugger-interfaces"></a>Rozhraní ladicího programu aktivních skriptů
Soubory hlaviček activdbg.h a activdbg100.h poskytují rozhraní, výčty a struktury uvedené v této části. Jsou pro ladění skriptu.  
  
> [!NOTE]
>  `IJSDebug*` Rozhraní a `IEnumJsStackFrames` rozhraní nejprve uvolnila v Internet Exploreru 11 pro ladění nativního kódu pomocí skriptu. V záhlaví souboru tato rozhraní je jscript9diag.h.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 Následující rozhraní povolit jazykově neutrální, hostitele jazykově neutrální ladění:  
  
-   [Konstanty ladicího programu aktivních skriptů, výčty a struktury](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)  
  
-   [Iactivescriptdebug – rozhraní](../../winscript/reference/iactivescriptdebug-interface.md)  
  
-   [Iactivescripterrordebug – rozhraní](../../winscript/reference/iactivescripterrordebug-interface.md)  
  
-   [Iactivescripterrordebug110 – rozhraní](../../winscript/reference/iactivescripterrordebug110-interface.md)  
  
-   [Iactivescriptsitedebug – rozhraní](../../winscript/reference/iactivescriptsitedebug-interface.md)  
  
-   [IActiveScriptSiteDebug32 rozhraní](../../winscript/reference/iactivescriptsitedebug32-interface.md)  
  
-   [Iactivescriptsitedebugex – rozhraní](../../winscript/reference/iactivescriptsitedebugex-interface.md)  
  
-   [Iactivescriptwinrterrordebug – rozhraní](../../winscript/reference/iactivescriptwinrterrordebug-interface.md)  
  
-   [Iapplicationdebugger – rozhraní](../../winscript/reference/iapplicationdebugger-interface.md)  
  
-   [Iapplicationdebuggerui – rozhraní](../../winscript/reference/iapplicationdebuggerui-interface.md)  
  
-   [Idebugapplication – rozhraní](../../winscript/reference/idebugapplication-interface.md)  
  
-   [Idebugapplication110 – rozhraní](../../winscript/reference/idebugapplication110-interface.md)  
  
-   [Idebugapplicationnode – rozhraní](../../winscript/reference/idebugapplicationnode-interface.md)  
  
-   [Idebugapplicationnode100 – rozhraní](../../winscript/reference/idebugapplicationnode100-interface.md)  
  
-   [Idebugapplicationnodeevents – rozhraní](../../winscript/reference/idebugapplicationnodeevents-interface.md)  
  
-   [Idebugapplicationthread – rozhraní](../../winscript/reference/idebugapplicationthread-interface.md)  
  
-   [Idebugapplicationthread110 – rozhraní](../../winscript/reference/idebugapplicationthread110-interface.md)  
  
-   [Idebugapplicationthreadevents110 – rozhraní](../../winscript/reference/idebugapplicationthreadevents110-interface.md)  
  
-   [Idebugasyncoperation – rozhraní](../../winscript/reference/idebugasyncoperation-interface.md)  
  
-   [Idebugasyncoperationcallback – rozhraní](../../winscript/reference/idebugasyncoperationcallback-interface.md)  
  
-   [Idebugcodecontext – rozhraní](../../winscript/reference/idebugcodecontext-interface.md)  
  
-   [Idebugcookie – rozhraní](../../winscript/reference/idebugcookie-interface.md)  
  
-   [Idebugdocument – rozhraní](../../winscript/reference/idebugdocument-interface.md)  
  
-   [Idebugdocumentcontext – rozhraní](../../winscript/reference/idebugdocumentcontext-interface.md)  
  
-   [Idebugdocumenthelper – rozhraní](../../winscript/reference/idebugdocumenthelper-interface.md)  
  
-   [Idebugdocumenthost – rozhraní](../../winscript/reference/idebugdocumenthost-interface.md)  
  
-   [Idebugdocumentinfo – rozhraní](../../winscript/reference/idebugdocumentinfo-interface.md)  
  
-   [Idebugdocumentprovider – rozhraní](../../winscript/reference/idebugdocumentprovider-interface.md)  
  
-   [Idebugdocumenttext – rozhraní](../../winscript/reference/idebugdocumenttext-interface.md)  
  
-   [Idebugdocumenttextauthor – rozhraní](../../winscript/reference/idebugdocumenttextauthor-interface.md)  
  
-   [Idebugdocumenttextevents – rozhraní](../../winscript/reference/idebugdocumenttextevents-interface.md)  
  
-   [Idebugdocumenttextexternalauthor – rozhraní](../../winscript/reference/idebugdocumenttextexternalauthor-interface.md)  
  
-   [Idebugexpression – rozhraní](../../winscript/reference/idebugexpression-interface.md)  
  
-   [Idebugexpressioncallback – rozhraní](../../winscript/reference/idebugexpressioncallback-interface.md)  
  
-   [Idebugexpressioncontext – rozhraní](../../winscript/reference/idebugexpressioncontext-interface.md)  
  
-   [Idebugformatter – rozhraní](../../winscript/reference/idebugformatter-interface.md)  
  
-   [Idebughelper – rozhraní](../../winscript/reference/idebughelper-interface.md)  
  
-   [Idebugsessionprovider – rozhraní](../../winscript/reference/idebugsessionprovider-interface.md)  
  
-   [Idebugsessionproviderex – rozhraní](../../winscript/reference/idebugsessionproviderex-interface.md)  
  
-   [Idebugstackframe – rozhraní](../../winscript/reference/idebugstackframe-interface.md)  
  
-   [Idebugstackframesniffer – rozhraní](../../winscript/reference/idebugstackframesniffer-interface.md)  
  
-   [Idebugstackframesnifferex – rozhraní](../../winscript/reference/idebugstackframesnifferex-interface.md)  
  
-   [Idebugsyncoperation – rozhraní](../../winscript/reference/idebugsyncoperation-interface.md)  
  
-   [Idebugthreadcall – rozhraní](../../winscript/reference/idebugthreadcall-interface.md)  
  
-   [Ienumdebugapplicationnodes – rozhraní](../../winscript/reference/ienumdebugapplicationnodes-interface.md)  
  
-   [Ienumdebugcodecontexts – rozhraní](../../winscript/reference/ienumdebugcodecontexts-interface.md)  
  
-   [Ienumdebugexpressioncontexts – rozhraní](../../winscript/reference/ienumdebugexpressioncontexts-interface.md)  
  
-   [Ienumdebugstackframes – rozhraní](../../winscript/reference/ienumdebugstackframes-interface.md)  
  
-   [Ienumjsstackframes – rozhraní](../../winscript/reference/ienumjsstackframes-interface.md)  
  
-   [Ienumremotedebugapplications – rozhraní](../../winscript/reference/ienumremotedebugapplications-interface.md)  
  
-   [Ienumremotedebugapplicationthreads – rozhraní](../../winscript/reference/ienumremotedebugapplicationthreads-interface.md)  
  
-   [Ijsdebug – rozhraní](../../winscript/reference/ijsdebug-interface.md)  
  
-   [Ijsdebugbreakpoint – rozhraní](../../winscript/reference/ijsdebugbreakpoint-interface.md)  
  
-   [Ijsdebugdatatarget – rozhraní](../../winscript/reference/ijsdebugdatatarget-interface.md)  
  
-   [Ijsdebugframe – metoda](../../winscript/reference/ijsdebugframe-interface.md)  
  
-   [Ijsdebugprocess – rozhraní](../../winscript/reference/ijsdebugprocess-interface.md)  
  
-   [Ijsdebugproperty – rozhraní](../../winscript/reference/ijsdebugproperty-interface.md)  
  
-   [Ijsdebugstackwalker – rozhraní](../../winscript/reference/ijsdebugstackwalker-interface.md)  
  
-   [Ijsenumdebugproperty – rozhraní](../../winscript/reference/ijsenumdebugproperty-interface.md)  
  
-   [Imachinedebugmanager – rozhraní](../../winscript/reference/imachinedebugmanager-interface.md)  
  
-   [Imachinedebugmanagercookie – rozhraní](../../winscript/reference/imachinedebugmanagercookie-interface.md)  
  
-   [Imachinedebugmanagerevents – rozhraní](../../winscript/reference/imachinedebugmanagerevents-interface.md)  
  
-   [Iprocessdebugmanager – rozhraní](../../winscript/reference/iprocessdebugmanager-interface.md)  
  
-   [Iprovideexpressioncontexts – rozhraní](../../winscript/reference/iprovideexpressioncontexts-interface.md)  
  
-   [Iremotedebugapplication – rozhraní](../../winscript/reference/iremotedebugapplication-interface.md)  
  
-   [Iremotedebugapplication110 – rozhraní](../../winscript/reference/iremotedebugapplication110-interface.md)  
  
-   [Iremotedebugapplicationex – rozhraní](../../winscript/reference/iremotedebugapplicationex-interface.md)  
  
-   [Iremotedebugapplicationevents – rozhraní](../../winscript/reference/iremotedebugapplicationevents-interface.md)  
  
-   [Iremotedebugapplicationthread – rozhraní](../../winscript/reference/iremotedebugapplicationthread-interface.md)  
  
-   [Iremotedebugapplicationthreadex – rozhraní](../../winscript/reference/iremotedebugapplicationthreadex-interface.md)  
  
-   [Isetnextstatement – rozhraní](../../winscript/reference/isetnextstatement-interface.md)  
  
-   [Isimpleconnectionpoint – rozhraní](../../winscript/reference/isimpleconnectionpoint-interface.md)  
  
-   [Iwebappdiagnosticssetup – rozhraní](../../winscript/reference/iwebappdiagnosticssetup-interface.md)  
  
-   [Iwebappdiagnosticsobjectinitialization – rozhraní](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md)  
  
 V následující části jsou uvedeny konstanty, výčty a struktury slouží k ladění:  
  
-   [Konstanty ladicího programu aktivních skriptů, výčty a struktury](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)  
  
## <a name="see-also"></a>Viz také  
 [Přehled ladění aktivních skriptů](../../winscript/active-script-debugging-overview.md)