---
title: "Implementace pomocných rozhraní inteligentního hostitele | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Smart Host Helper Interfaces, implementing
ms.assetid: b9c44246-4d4d-469e-91be-00c8f5796fa5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba571f6ad66855c44902e06467889e2cae5b4555
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="implementing-smart-host-helper-interfaces"></a>Implementace pomocných rozhraní inteligentního hostitele
[Idebugdocumenthelper – rozhraní](../winscript/reference/idebugdocumenthelper-interface.md) rozhraní výrazně zjednodušuje vytvoření inteligentního hostitele pro aktivní ladění, protože poskytuje implementace pro mnoho rozhraní nutná pro inteligentní hostování.  
  
 Chcete-li být inteligentního hostitele pomocí `IDebugDocumentHelper`, hostitelskou aplikaci musíte udělat jenom tři věci:  
  
1.  `CoCreate`Proces ladění správce a použijte [iprocessdebugmanager – rozhraní](../winscript/reference/iprocessdebugmanager-interface.md) rozhraní pro přidání aplikace do seznamu debuggable aplikací.  
  
2.  Vytvoření dokumentu pomocné rutiny ladění pro každý skript objektu, pomocí [IProcessDebugManager::CreateDebugDocumentHelper](../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md) metoda. Zajistěte, aby definovaný název dokumentu, nadřazený dokument, text a blocích skriptu.  
  
3.  Implementace [iactivescriptsitedebug – rozhraní](../winscript/reference/iactivescriptsitedebug-interface.md) rozhraní na vaše objekt, který implementuje [iactivescriptsite –](../winscript/reference/iactivescriptsite.md) rozhraní (která je potřebná pro aktivní skriptování). Metodu pouze netriviální na `IActiveScriptSiteDebug` rozhraní jednoduše deleguje do pomocné rutiny.  
  
 Volitelně můžete implementovat hostitele [idebugdocumenthost – rozhraní](../winscript/reference/idebugdocumenthost-interface.md) rozhraní Pokud potřebuje další kontrolu nad syntaxe barvu, vytváření kontextu dokumentů a další rozšířené funkce.  
  
 Hlavní omezení na pomocná inteligentního hostitele je, že zpracovávat jen dokumentů, jejichž obsah změnit nebo zmenšit po byly přidány (i když můžete rozšířit dokumentů). Pro mnoho inteligentního hostitele ale funkce, které poskytuje je přesně co je potřeba.  
  
 Následující části popisují každý krok podrobněji.  
  
## <a name="create-an-application-object"></a>Vytvoření objektu služby aplikace  
 Před použitím Pomocník inteligentního hostitele, je třeba vytvořit [idebugapplication – rozhraní](../winscript/reference/idebugapplication-interface.md) objekt představující aplikace v ladicím programu.  
  
#### <a name="to-create-an-application-object"></a>Chcete-li vytvořit objekt aplikace  
  
1.  Vytvoření instance procesu ladění manager pomocí `CoCreateInstance`.  
  
2.  Volání [IProcessDebugManager::CreateApplication](../winscript/reference/iprocessdebugmanager-createapplication.md).  
  
3.  Nastavit název u aplikace pomocí [IDebugApplication::SetName](../winscript/reference/idebugapplication-setname.md).  
  
4.  Přidání objekt aplikace do seznamu debuggable aplikací s použitím [IProcessDebugManager::AddApplication](../winscript/reference/iprocessdebugmanager-addapplication.md).  
  
     Následující kód popisuje proces, ale nezahrnuje Kontrola chyb nebo jinými technikami, robustní programování.  
  
    ```  
    CoCreateInstance(CLSID_ProcessDebugManager, NULL,  
          CLSCTX_INPROC_SERVER | CLSCTX_INPROC_HANDLER  
          | CLSCTX_LOCAL_SERVER,  
    IID_IProcessDebugManager, (void **)&g_ppdm);  
    g_ppdm->CreateApplication(&g_pda);  
    g_pda->SetName(L"My cool application");  
    g_ppdm->AddApplication(g_pda, &g_dwAppCookie);  
    ```  
  
## <a name="using-idebugdocumenthelper"></a>Idebugdocumenthelper – použití  
  
#### <a name="to-use-the-helper-minimal-sequence-of-steps"></a>Chcete-li použít pomocníka (minimální pořadí kroků)  
  
1.  Pro každý dokument hostitele vytvořit pomocné rutiny pomocí [IProcessDebugManager::CreateDebugDocumentHelper](../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md).  
  
2.  Volání [IDebugDocumentHelper::Init](../winscript/reference/idebugdocumenthelper-init.md) na pomocné rutiny, která poskytuje název, atributy dokumentu a tak dále.  
  
3.  Volání [IDebugDocumentHelper::Attach](../winscript/reference/idebugdocumenthelper-attach.md) s nadřazenou Pomocník pro dokument (nebo hodnota NULL, pokud dokument je kořenový adresář) definovat umístění dokumentu. ve stromové struktuře a zpřístupněte ho ladicího programu.  
  
4.  Volání [IDebugDocumentHelper::AddDBCSText](../winscript/reference/idebugdocumenthelper-adddbcstext.md) nebo [IDebugDocumentHelper::AddUnicodeText](../winscript/reference/idebugdocumenthelper-addunicodetext.md) zadat text dokumentu. (Toto můžete volat vícekrát, pokud dokument je stažen postupně, jako v případě prohlížeče.)  
  
5.  Volání [IDebugDocumentHelper::DefineScriptBlock](../winscript/reference/idebugdocumenthelper-definescriptblock.md) definovat rozsahy adres pro každého bloku skriptu a přidružené skriptovací stroje.  
  
## <a name="implementing-iactivescriptsitedebug"></a>Iactivescriptsitedebug – implementace  
 K implementaci [IActiveScriptSiteDebug::GetDocumentContextFromPosition](../winscript/reference/iactivescriptsitedebug-getdocumentcontextfromposition.md), získat pomocné rutiny odpovídající dané lokality a potom získat výchozí dokument posunutí pro daný kontext zadaná zdrojová následujícím způsobem:  
  
```  
pddh->GetScriptBlockInfo(dwSourceContext, NULL, &ulStartPos, NULL);  
```  
  
 Potom pomocí této pomocné rutiny k vytvoření nového dokumentu kontextu daného znaku posunu:  
  
```  
pddh->CreateDebugDocumentContext(ulStartPos + uCharacterOffset, cChars, &pddcNew);  
```  
  
 K implementaci [IActiveScriptSiteDebug::GetRootApplicationNode](../winscript/reference/iactivescriptsitedebug-getrootapplicationnode.md), jednoduše volání `IDebugApplication::GetRootNode` (zděděno z [IRemoteDebugApplication::GetRootNode](../winscript/reference/iremotedebugapplication-getrootnode.md)).  
  
 K implementaci [IDebugDocumentHelper::GetDebugApplicationNode](../winscript/reference/idebugdocumenthelper-getdebugapplicationnode.md), jednoduše vrátí `IDebugApplication` jste původně vytvořili pomocí Správce ladění procesu.  
  
## <a name="the-optional-idebugdocumenthost-interface"></a>Volitelné idebugdocumenthost – rozhraní  
 Hostitel může poskytnout implementaci [idebugdocumenthost – rozhraní](../winscript/reference/idebugdocumenthost-interface.md) pomocí [IDebugDocumentHelper::SetDebugDocumentHost](../winscript/reference/idebugdocumenthelper-setdebugdocumenthost.md) jí přidělit další kontrolu nad pomocné rutiny. Tady jsou některé z klíčových věcí rozhraní hostitele umožňuje provádět:  
  
-   Přidat pomocí textového [IDebugDocumentHelper::AddDeferredText](../winscript/reference/idebugdocumenthelper-adddeferredtext.md) tak, aby hostitel není nutné poskytovat skutečnými znaky okamžitě. V případě skutečně potřeby znaky jsou pomocné rutiny zavolá [IDebugDocumentHost::GetDeferredText](../winscript/reference/idebugdocumenthost-getdeferredtext.md) na hostiteli.  
  
-   Přepište výchozí barevné zvýrazňování syntaxe poskytované pomocné rutiny. Volání pomocné rutiny [IDebugDocumentHost::GetScriptTextAttributes](../winscript/reference/idebugdocumenthost-getscripttextattributes.md) k určení barevné zvýrazňování pro rozsah znaků, návratem zpět na jeho výchozí implementace, pokud hostitel vrátí `E_NOTIMPL`.  
  
-   Zadejte řízení Neznámý pro dokument kontexty vytvořené pomocné rutiny implementací [IDebugDocumentHost::OnCreateDocumentContext](../winscript/reference/idebugdocumenthost-oncreatedocumentcontext.md). To umožňuje hostitelů pro přepsání funkce výchozí dokument kontextu implementace.  
  
-   Zadejte název cesty v systému souborů pro dokument. Některé ladění uživatelská použít k povolení uživatelům upravit a uložit změny do dokumentu. [IDebugDocumentHost::NotifyChanged](../winscript/reference/idebugdocumenthost-notifychanged.md) je volána po uložení dokumentu oznámit hostitele.  
  
## <a name="see-also"></a>Viz také  
 [Přehled ladění aktivních skriptů](../winscript/active-script-debugging-overview.md)