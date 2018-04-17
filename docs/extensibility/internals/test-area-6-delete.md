---
title: 'Testovací oblasti 6: Odstranit | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], deleting items
- source control plug-ins, deleting items
ms.assetid: 6f2e872c-5ba2-4303-9f50-a90cef9a6225
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 97fc6ab9746e7ef2188c78dc77ec357f7d415a42
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="test-area-6-delete"></a>Testování oblasti 6: odstranění
Tato oblast modulu plug-in testovací zdrojového kódu zahrnuje akce odstranění.  
  
 Správa zdrojového kódu odpoví na odstranění akcí v **Průzkumníku řešení**.  
  
 Následuje seznam položek, které je možné odstranit:  
  
-   Soubory  
  
-   Složky  
  
-   Projekt  
  
 V závislosti na typu projektu, můžete mít možnost **odebrat** projektu (soubory na disku zůstanou) nebo **odstranit** projektu (odebere soubory na disku). Obě tyto akce odebere projektu nebo položku z **Průzkumníku řešení**.  
  
## <a name="expected-behavior"></a>Očekávané chování  
 Je očekávané chování u testovacích případů v testovací oblasti odstranit:  
  
-   Odstraněné položky se už nebude viditelné v rámci **Průzkumníku řešení**.  
  
-   Nadřazené odstraněný projekt nebo položka je rezervována podle potřeby (případně s výzvou.)  
  
-   Po odstranění rezervovaný limit nebo přidat položky, nezobrazí v **čeká na vrácení se změnami** okno.  
  
-   Položka stále existuje v rámci ovládacího prvku jako zdrojové úložiště i po jejím odstranění a musí být ručně odstraněna.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Odstranění projektu klienta|1.  Vytvoření projektu klienta.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Odeberte celý projekt z řešení|Běžné očekávané chování.|  
|Odstranit prázdný soubor|1.  Vytvoření projektu klienta.<br />2.  Přidejte do projektu soubor nula bajtů.<br />3.  Přidáte řešení do správy zdrojového kódu.<br />4.  Vyberte soubor, odstraňte jej.|Běžné očekávané chování.|  
|Odstranění složky s jedním souborem|1.  Vytvořte jeden projekt řešení.<br />2.  Přidáte složku.<br />3.  Přidáte jeden soubor do složky.<br />4.  Přidáte řešení do správy zdrojového kódu.<br />5.  Podívejte se na projektu výzev.<br />6.  Odstraňte složku.|Běžné očekávané chování.|  
|Odstranění souboru systému webového projektu|1.  Vytvořte projekt webového systému souborů (použijte na tlačítko Procházet a zadejte cestu UNC).<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Odeberte celý projekt z řešení.<br />4.  Opakujte kroky 1 až 3 pro místní webového projektu (vykonává různé cesty prostřednictvím kód, ale má stejné externí rozhraní a chování).|Běžné očekávané chování.|  
|Odstranění souboru z webového systému souboru projektu|1.  Vytvořte soubor systém webového projektu.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Odstranění souboru z projektu.<br />4.  Opakujte kroky 1 až 3 pro místní webového projektu (vykonává různé cesty prostřednictvím kód, ale má stejné externí rozhraní a chování).|Běžné očekávané chování.|  
  
## <a name="see-also"></a>Viz také  
 [Testovací příručka pro moduly plug-in správy zdrojového kódu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)