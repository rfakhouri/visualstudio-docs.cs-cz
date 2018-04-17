---
title: 'Testovací oblasti 8: Modul Plug-in přepínání | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], switching plug-ins
- source control plug-ins, switching
ms.assetid: 01370792-b5da-4e46-9ce2-7dd326587141
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 534bd9338181c5b682779b62a9c118a5ccaf8cda
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="test-area-8-plug-in-switching"></a>Testovací oblasti 8: Modul Plug-in přepínání
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Integrované vývojové prostředí (IDE) má uživatelské rozhraní (UI) Chcete-li změnit aktuální modul plug-in zdrojového kódu. Tato oblast testovací poskytuje testovacích případů pro proces výběr, který chcete použít pro řešení správy zdrojového kódu modulu plug-in.  
  
## <a name="command-menu-access"></a>Příkaz přístup do nabídky  
 Následující [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] cesty nabídky integrované vývojové prostředí se používají v testovací případy.  
  
-   Aktuální modul plug-in správy zdroje: **nástroje** -> **možnosti** -> **správy zdrojového kódu** -> **výběr modulu Plug-in** .  
  
-   Zdroj změny řízení vazby: **soubor** -> **správy zdrojového kódu** -> **změnu zdrojového kódu**...  
  
## <a name="common-expected-behavior"></a>Běžné očekávané chování  
 Změna modulu plug-in pro řešení zdrojového kódu je možné bez ukončení Visual Studio nebo opětovném načtení řešení. Kromě toho modul plug-in aktuální zdrojového kódu se automaticky změní na používaný řešením při načtení tohoto řešení.  
  
## <a name="test-cases"></a>Testovací případy  
 Níže jsou uvedeny konkrétní testovací případy pro modul plug-in přepínání testovací oblast.  
  
### <a name="case-8a-automatic-change"></a>Případ 8a: Automatická změna  
  
#### <a name="expected-behavior"></a>Očekávané chování  
 Pokud uživatel načítá řešení, které je ve správě zdrojů, řešení je automaticky načíst a modul plug-in správy příslušné zdroje je vybrán jako aktuální.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Modul plug-in změnu automatické zdroj ovládacího prvku|1.  Vyberte modul plug-in pod testování jako aktuální (**nástroje** -> **možnosti** -> **správy zdrojového kódu** -> **modulu Plug-in Výběr**.)<br />2.  Vytvořte nový projekt.<br />3.  Přidáte řešení do správy zdrojového kódu.<br />4.  Vyberte jiný modul plug-in (například [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />5.  Přijetí výzvy uvolnění řešení.<br />6.  Opětovným otevřením daného řešení z disku.|Je řešení otevřené.<br /><br /> Modul plug-in testovaného je modul plug-in aktuální zdrojového kódu.|  
  
### <a name="case-8b-solution-based-change"></a>Případ 8b: na základě řešení změn  
  
#### <a name="expected-behavior"></a>Očekávané chování  
 Řešení může mít jeho přidružené modul plug-in správy zdroje změnit.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Změna modulu plug-in pro řešení|1.  Vyberte modul plug-in pod testování jako aktuální (**nástroje** -> **možnosti** -> **správy zdrojového kódu** -> **modulu Plug-in Výběr**).<br />2.  Vytvořte nový projekt a řešení.<br />3.  Přidáte řešení do správy zdrojového kódu.<br />4.  Odpojení od správy zdrojového kódu řešení (pomocí **změnu zdrojového kódu** dialogové okno).<br />5.  Vyberte jiný modul plug-in (například [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />6.  Znovu načte řešení z disku, pokud odpojeno.<br />7.  Přidáte řešení do správy zdrojového kódu.<br />8.  Odpojení od správy zdrojového kódu řešení (pomocí **změnu zdrojového kódu** dialogové okno).<br />9. Vyberte modul plug-in testovaného znovu.<br />10. Znovu načte řešení z disku, pokud odpojeno.<br />11. Vytvoření vazby řešení do původního umístění (pomocí **změnu zdrojového kódu** dialogové okno).|Řešení se přidá do správy zdrojového kódu s použitím vybraný modul plug-in.|  
  
## <a name="see-also"></a>Viz také  
 [Testovací příručka pro moduly plug-in správy zdrojového kódu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)