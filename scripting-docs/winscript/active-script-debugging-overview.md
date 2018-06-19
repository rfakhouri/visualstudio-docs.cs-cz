---
title: Přehled ladění aktivních skriptů | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Active Script Debugging overview
ms.assetid: ce4ec768-d017-4dfa-a7e3-cced3a29e679
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1d9aebdc3f8fa4df0f4386609e632e1a8611c87f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792369"
---
# <a name="active-script-debugging-overview"></a>Přehled ladění aktivních skriptů
Rozhraní Active ladění skriptů povolit jazykově neutrální, hostitele jazykově neutrální ladění a podporují celou řadu vývojové prostředí.  
  
 ![Skript hostitelský proces](../winscript/media/scp56activdbgarchgif.gif "Scp56ActivDbgArchgif")  
Obrázek 1  
  
 Prostředí ladění jazykově neutrální může podporovat všechny programovací jazyk nebo směs programovacích jazyků, bez nutnosti specifické znalosti kterékoli z těchto jazyků. Ladění prostředí také podporuje krokování s mezi jazyky a zarážky. (V tomto přehledu se zaměřují hlavně na podporu skriptovací jazyky, jako je VBScript a [!INCLUDE[javascript](../javascript/includes/javascript-md.md)].)  
  
 Ladicí program hostitele jazykově neutrální můžete být automaticky použita s libovolným hostitelem aktivní skriptování, jako je například Internet Explorer nebo vlastního hostitele. Hostitel Určuje, co ladicí program zobrazí uživateli, z struktura stromu dokumentu do obsahu a barevné zvýrazňování syntaxe dokumentů ladění. To umožňuje vyladěnou zdrojový kód zobrazený v kontextu hostitele dokumentu. Internet Explorer můžete například zobrazit skript na stránce HTML.  
  
 V níže uvedené témata jsou popsané jednotlivé komponenty klíče v Active ladění a jeho přidružené rozhraní. Nicméně než budete pokračovat, musí být definován několik klíčových konceptů Active ladění:  
  
 hostitelskou aplikaci  
 Aplikace, která hostuje skript motorů a poskytuje Skriptovatelná sadu objektů (nebo "model objektu").  
  
 modul jazyka  
 Komponenta, která poskytuje analýza, spuštění a ladění abstrakci pro konkrétní jazyk.  
  
 ladicí program IDE  
 Aplikace, která umožňuje komunikaci s hostiteli aplikace a jazyk motory ladění uživatelského rozhraní.  
  
 Správce počítače ladění  
 Komponenta, která udržuje registr procesů debuggable aplikace.  
  
 Správce procesu ladění  
 Komponenty, která udržuje stromu debuggable dokumentů pro konkrétní aplikaci, sleduje spuštěných vláken a tak dále.  
  
 kontext dokumentu  
 Kontext dokumentu je abstrakcí představující konkrétní rozsah ve zdrojovém kódu dokumentu hostitele.  
  
 kontext kódu  
 Představuje kontext kódu konkrétní umístění v spuštěním kódu jazyka stroje ("virtuální instrukce ukazatel".)  
  
 výraz kontextu  
 Konkrétní kontextu (například rámce zásobníku) ve kterém může být vyhodnotí výrazy pomocí modulu jazyka.  
  
 objekt procházení  
 Strukturovaných, nezávislé na jazyku reprezentace objektu název, typ, hodnotu a dílčí objekty, které jsou vhodné pro implementaci "okno kukátka" uživatelského rozhraní.  
  
 Dole je přehled všechny klíčové komponenty Active ladění a odpovídající, přidružené rozhraní, za nímž následuje podrobnosti o těchto rozhraní.  
  
## <a name="language-engine"></a>Modul jazyka  
 Poskytuje modul jazyka:  
  
-   Analýza jazyk a spouštění.  
  
-   Podpora ladění (zarážky a tak dále).  
  
-   Vyhodnocení výrazu.  
  
-   Barevné zvýrazňování syntaxe.  
  
-   Objekt, procházení.  
  
-   Výčet zásobníku a analýze.  
  
 V následující tabulce jsou rozhraní, která skriptovací stroj musí podporovat zajistit ladění, vyhodnocení výrazu a procházení objekt. Tato rozhraní jsou používány hostitelskou aplikaci k mapování mezi jeho kontextu dokumentu a kontexty kódu stroje a také pomocí ladicího programu uživatelského rozhraní udělat vyhodnocení výrazu zásobníku – výčet a objekt procházení.  
  
 [Iactivescriptdebug – rozhraní](../winscript/reference/iactivescriptdebug-interface.md)  
 Poskytuje kontext výčtu kód a barevné zvýrazňování syntaxe.  
  
 [Iactivescripterrordebug – rozhraní](../winscript/reference/iactivescripterrordebug-interface.md)  
 Vrátí dokumentů kontexty a rámce zásobníku chyb.  
  
 [Iactivescriptsitedebug – rozhraní](../winscript/reference/iactivescriptsitedebug-interface.md)  
 Hostitel zadaný odkaz z skriptovací stroj ladicí program.  
  
 [Idebugcodecontext – rozhraní](../winscript/reference/idebugcodecontext-interface.md)  
 Poskytuje virtuální "ukazatel instrukce" v vlákna.  
  
 [Ienumdebugcodecontexts – rozhraní](../winscript/reference/ienumdebugcodecontexts-interface.md)  
 Vytvoří výčet kontexty kódu, které odpovídají kontextu dokumentu.  
  
 [Idebugstackframe – rozhraní](../winscript/reference/idebugstackframe-interface.md)  
 Představuje logické zásobníku v zásobníku přístup z více vláken.  
  
 [Idebugexpressioncontext – rozhraní](../winscript/reference/idebugexpressioncontext-interface.md)  
 Poskytuje kontext, ve kterém můžete vyhodnotí výrazy.  
  
 [Idebugstackframesniffer – rozhraní](../winscript/reference/idebugstackframesniffer-interface.md)  
 Poskytuje způsob, jak vytvořit výčet rámce zásobníku logické.  
  
 [Idebugexpression – rozhraní](../winscript/reference/idebugexpression-interface.md)  
 Představuje asynchronně vyhodnocený výraz.  
  
 [Idebugsyncoperation – rozhraní](../winscript/reference/idebugsyncoperation-interface.md)  
 Umožňuje skriptovací stroj abstrahovat operace, která je nutné provést při vnořených v konkrétní blokované vlákna.  
  
 [Idebugasyncoperation – rozhraní](../winscript/reference/idebugasyncoperation-interface.md)  
 Poskytuje asynchronní přístup k operaci synchronní ladění.  
  
 [Idebugasyncoperationcallback – rozhraní](../winscript/reference/idebugasyncoperationcallback-interface.md)  
 Poskytuje stav události související s průběh `IDebugAsyncOperation` rozhraní vyhodnocení.  
  
 [Ienumdebugexpressioncontexts – rozhraní](../winscript/reference/ienumdebugexpressioncontexts-interface.md)  
 Vytvoří výčet kolekce `IDebugExpressionContexts` objekty.  
  
 [Iprovideexpressioncontexts – rozhraní](../winscript/reference/iprovideexpressioncontexts-interface.md)  
 Poskytuje způsob, jak vytvořit výčet výraz kontexty známé některých součástí.  
  
 [Idebugformatter – rozhraní](../winscript/reference/idebugformatter-interface.md)  
 Umožňuje, aby jazyk nebo rozhraní IDE pro přizpůsobení převod mezi hodnot typu VARIANT nebo VARTYPE typy a řetězci.  
  
 [Idebugstackframesnifferex – rozhraní](../winscript/reference/idebugstackframesnifferex-interface.md)  
 Vytvoří výčet rámce logické zásobníku pro PDM.  
  
## <a name="hosts"></a>Hostitelé  
 Hostiteli:  
  
-   Hostuje moduly jazyka.  
  
-   Poskytuje model objektů (sadu objektů, které mohou být skripty).  
  
-   Definuje stromu dokumentů, které můžete ladit a jejich obsah.  
  
-   Slouží k uspořádání skripty do virtuální aplikace.  
  
 Existují dva typy hostitelů:  
  
-   Vlečný hostitel podporuje jenom základní aktivní skriptování rozhraní. Nemá žádnou kontrolu nad strukturu dokumentu nebo organizace; To je dáno zcela skripty pro moduly jazyka.  
  
-   Inteligentního hostitele podporuje větší sadu rozhraní, která umožňuje definovat stromu dokumentu, obsah dokumentu a barevné zvýrazňování syntaxe. Existuje sada rozhraní pomocné rutiny, popsané v následující dílčí části, které bylo mnohem snazší pro hostitele jako inteligentního hostitele.  
  
### <a name="smart-host-helper-interfaces"></a>Pomocník hostitele čipové rozhraní  
 `IDebugDocumentHelper` Metody poskytují sadu značně zjednodušené rozhraní, můžete získat výhody v podobě čipové hostování bez zpracování úplné složitost (a power) rozhraní úplné hostitele hostitele.  
  
 Hostitel není potřeba samozřejmě použijte tato rozhraní. Ale pomocí těchto rozhraní se můžete vyhnout implementace nebo s počtem složitější rozhraní.  
  
 [Idebugdocumenthelper – rozhraní](../winscript/reference/idebugdocumenthelper-interface.md)  
 Implementované PDM a poskytuje implementaci pro mnoho rozhraní nutná pro inteligentní hostování.  
  
 [Idebugdocumenthost – rozhraní](../winscript/reference/idebugdocumenthost-interface.md)  
 (Volitelně) implementované hostitele vystavit hostiteli specifické funkce, například k ladicího programu zvýrazňování syntaxe.  
  
 Další informace najdete v tématu [implementace pomocných rozhraní ke inteligentního hostitele](../winscript/implementing-smart-host-helper-interfaces.md).  
  
### <a name="full-smart-host-interfaces"></a>Rozhraní úplné čipové hostitele  
 Níže je kompletní sada rozhraní, které hostitel čipové musí implementovat nebo použijte, pokud nepoužívá rozhraní pomocné rutiny.  
  
 Rozhraní implementované hostitele:  
  
 [Idebugdocumentinfo – rozhraní](../winscript/reference/idebugdocumentinfo-interface.md)  
 Obsahuje informace o dokumentu, který může nebo nemusí být vytvořena instance.  
  
 [Idebugdocumentprovider – rozhraní](../winscript/reference/idebugdocumentprovider-interface.md)  
 Poskytuje prostředky pro vytvoření instance dokumentu na vyžádání.  
  
 [Idebugdocument – rozhraní](../winscript/reference/idebugdocument-interface.md)  
 Základní rozhraní pro všechny dokumenty ladění.  
  
 [Idebugdocumenttext – rozhraní](../winscript/reference/idebugdocumenttext-interface.md)  
 Poskytuje přístup k verzi dokumentu ladění prostého textu.  
  
 [Idebugdocumenttextauthor – rozhraní](../winscript/reference/idebugdocumenttextauthor-interface.md)  
 Umožňuje úpravu textovém verzi dokumentu ladění.  
  
 [Idebugdocumentcontext – rozhraní](../winscript/reference/idebugdocumentcontext-interface.md)  
 Poskytuje abstraktní reprezentací část laděné dokumentu.  
  
 Rozhraní implementované PDM jménem hostitele:  
  
 [Idebugapplicationnode – rozhraní](../winscript/reference/idebugapplicationnode-interface.md)  
 Rozšiřuje funkce `IDebugDocumentProvider` rozhraní tím, že poskytuje kontext v rámci stromu projektu.  
  
## <a name="debugger-ide"></a>ladicí program IDE  
 Prostředí IDE je nezávislé na jazyku ladění uživatelského rozhraní. Poskytuje:  
  
-   Editory nebo dokumentu prohlížeče.  
  
-   Breakpoint – Správa.  
  
-   Výraz vyhodnocování a sledování systému windows.  
  
-   Stack – procházení rámce.  
  
-   Objekt nebo třída procházení.  
  
-   Procházení strukturu virtuální aplikace.  
  
 Rozhraní implementované ladicí program:  
  
 [Iapplicationdebugger – rozhraní](../winscript/reference/iapplicationdebugger-interface.md)  
 Primární rozhraní vystavené relaci IDE ladicí program.  
  
 [Iapplicationdebuggerui – rozhraní](../winscript/reference/iapplicationdebuggerui-interface.md)  
 Externí komponenta dává větší kontrolu nad uživatelské rozhraní (UI) ladicího programu.  
  
 [Idebugexpressioncallback – rozhraní](../winscript/reference/idebugexpressioncallback-interface.md)  
 Poskytuje stav události pro `IDebugExpression` vyhodnocení průběh.  
  
 [Idebugdocumenttextevents – rozhraní](../winscript/reference/idebugdocumenttextevents-interface.md)  
 Poskytuje události indikující změny přidružené textového dokumentu.  
  
 [Idebugapplicationnodeevents – rozhraní](../winscript/reference/idebugapplicationnodeevents-interface.md)  
 Poskytuje rozhraní pro události `IDebugApplicationNode` rozhraní.  
  
### <a name="machine-debug-manager"></a>Machine Manager ladění  
 Ladění machine manager poskytuje bod spojení mezi virtuální aplikace a ladicí programy konfigurací a vytváření výčtu seznam aktivních virtuálních aplikací.  
  
 [Idebugsessionprovider – rozhraní](../winscript/reference/idebugsessionprovider-interface.md)  
 Vytvoří relaci ladění pro běžící aplikaci.  
  
 [Imachinedebugmanager – rozhraní](../winscript/reference/imachinedebugmanager-interface.md)  
 Primární rozhraní pro ladění správce počítače.  
  
 [Imachinedebugmanagercookie – rozhraní](../winscript/reference/imachinedebugmanagercookie-interface.md)  
 Podobně jako `IMachineDebugManager` rozhraní, ale toto rozhraní podporuje ladění soubory cookie.  
  
 [Imachinedebugmanagerevents – rozhraní](../winscript/reference/imachinedebugmanagerevents-interface.md)  
 Signály změny v běžícím seznam aplikací, které spravuje pomocí nástroje machine manager ladění.  
  
 [Ienumremotedebugapplications – rozhraní](../winscript/reference/ienumremotedebugapplications-interface.md)  
 Vytvoří výčet aplikace spuštěné v počítači.  
  
### <a name="process-debug-manager"></a>Správce procesu ladění  
 PDM provede následující akce:  
  
-   Synchronizuje ladění více modulů jazyk.  
  
-   Udržuje stromu debuggable dokumentů.  
  
-   Sloučení zásobníku.  
  
-   Souřadnice zarážky a zanoříte napříč strojů jazyka.  
  
-   Sleduje vláken.  
  
-   Udržuje vlákno ladicí program pro asynchronní zpracování.  
  
-   Komunikuje s machine manager ladění a ladicí program IDE.  
  
 Toto jsou rozhraní zajišťuje správce ladění procesu.  
  
 [Iprocessdebugmanager – rozhraní](../winscript/reference/iprocessdebugmanager-interface.md)  
 Primární rozhraní pro správce ladění procesu. Toto rozhraní můžete vytvořit, přidat nebo odebrat virtuální aplikace z procesu.  
  
 [Iremotedebugapplication – rozhraní](../winscript/reference/iremotedebugapplication-interface.md)  
 Představuje běžící aplikaci.  
  
 [Idebugapplication – rozhraní](../winscript/reference/idebugapplication-interface.md)  
 Zpřístupní-učinit vzdáleným ladění metody pro použití strojů jazyka a hostitele.  
  
 [Iremotedebugapplicationthread – rozhraní](../winscript/reference/iremotedebugapplicationthread-interface.md)  
 Představuje vlákno při provádění v rámci konkrétní aplikace.  
  
 [Idebugapplicationthread – rozhraní](../winscript/reference/idebugapplicationthread-interface.md)  
 Umožňuje strojů jazyka a hostitele, zadejte synchronizace vláken a spravovat informace specifické pro vlákno, ladění stavu.  
  
 [Ienumremotedebugapplicationthreads – rozhraní](../winscript/reference/ienumremotedebugapplicationthreads-interface.md)  
 Vytvoří výčet spuštěných vláken v aplikaci.  
  
 [Idebugthreadcall – rozhraní](../winscript/reference/idebugthreadcall-interface.md)  
 Odešle zařazené volání.  
  
 [Idebugapplicationnode – rozhraní](../winscript/reference/idebugapplicationnode-interface.md)  
 Udržuje pozice pro dokument v hierarchii.  
  
 [Ienumdebugapplicationnodes – rozhraní](../winscript/reference/ienumdebugapplicationnodes-interface.md)  
 Vytvoří výčet podřízené uzly uzlu přidružené aplikaci.  
  
 [Ienumdebugstackframes – rozhraní](../winscript/reference/ienumdebugstackframes-interface.md)  
 Vytvoří výčet rámce zásobníku odpovídající na vlákno, slučovány z motorů.  
  
 [Idebugcookie – rozhraní](../winscript/reference/idebugcookie-interface.md)  
 Umožňuje ladění souboru cookie ve skriptu ladicí programy.  
  
 [Idebughelper – rozhraní](../winscript/reference/idebughelper-interface.md)  
 Slouží jako objekt factory pro objekt prohlížeče a jednoduchý spojovací body pro moduly skriptu.  
  
 [Isimpleconnectionpoint – rozhraní](../winscript/reference/isimpleconnectionpoint-interface.md)  
 Poskytuje jednoduchý způsob pro popisující a výčet události aktivováno u konkrétní spojovací bod, pro moduly skriptu.  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní ladicího programu aktivních skriptů](../winscript/reference/active-script-debugger-interfaces.md)