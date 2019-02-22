---
title: Rychlé informace ve službě starší verze jazyka | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Quick Info, supporting in language services [managed package framework]
- IntelliSense, Quick Info
- language services [managed package framework], IntelliSense Quick Info
ms.assetid: 159ccb0b-f5d6-4912-b88b-e9612924ed5e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9d86ba3b75f2c0e26a568c962a51999dd9fac078
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56605962"
---
# <a name="quick-info-in-a-legacy-language-service"></a>Rychlé informace ve službě starší verze jazyka
Rychlé informace technologie IntelliSense zobrazuje informace o identifikátoru ve zdroji, když uživatel umístí identifikátor blikajícího kurzoru a vybere **rychlé informace** z **IntelliSense** nabídky, nebo drží ukazatel myši ukazatel myši identifikátor. To způsobí, že se zobrazí s informacemi o identifikátor popisku tlačítka. Tyto informace se obvykle skládá z typu identifier. Když je aktivní ladicí stroj, tyto informace mohou zahrnovat aktuální hodnotu. Ladicí stroj poskytuje hodnot výrazu, zatímco služba jazyka zpracovává jenom identifikátory.

 Služby starší verze jazyka jsou implementovány jako součást sady VSPackage, ale novější způsob implementace funkce služba jazyka je pro použití rozšíření MEF. Další informace najdete v tématu [názorný postup: Zobrazení popisky rychlé informace](../../extensibility/walkthrough-displaying-quickinfo-tooltips.md).

> [!NOTE]
>  Doporučujeme vám, že začnete používat nový editor API co nejdříve. Tím vylepšíme výkonu vaší služby jazyka a umožňují využívat nové funkce editoru.

 Třídy spravované balíček framework (MPF) jazyka služby poskytují plnou podporu pro zobrazení popisu rychlé informace technologie IntelliSense. Všechno, co musíte udělat, je zadat text, který se zobrazí a povolit funkci Rychlé informace.

 Text zobrazený je získán voláním <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda analyzátor s hodnotou z důvodu analýzy <xref:Microsoft.VisualStudio.Package.ParseReason>. Z tohoto důvodu určuje analyzátor získat informace o typu (nebo cokoli, co je třeba zobrazit v popisu tlačítka rychlé informace) pro identifikátor v umístění zadaném v <xref:Microsoft.VisualStudio.Package.ParseRequest> objektu. <xref:Microsoft.VisualStudio.Package.ParseRequest> Objekt je, co byl předán <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metody.

 Analyzátor musí analyzovat všechno, co do pozice v <xref:Microsoft.VisualStudio.Package.ParseRequest> objektu, aby bylo možné určit typy všechny identifikátory. Analyzátor pak musíte získat identifikátor v žádosti o umístění analýzy. Nakonec analyzátor musí projít nástroj tip data přidružená k této identifikátor, který <xref:Microsoft.VisualStudio.Package.AuthoringScope> objekt tohoto objektu můžete vrátit text z <xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDataTipText%2A> metody.

## <a name="enabling-the-quick-info-feature"></a>Povolení funkce Rychlé informace
 Pokud chcete povolit funkci Rychlé informace, je nutné nastavit `CodeSense` a `QuickInfo` pojmenované parametry <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute>. Nastavte tyto atributy <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> a <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableQuickInfo%2A> vlastnosti.

## <a name="implementing-the-quick-info-feature"></a>Implementace funkce Rychlé informace
 <xref:Microsoft.VisualStudio.Package.ViewFilter> Třída zpracovává operace rychlé informace technologie IntelliSense. Při <xref:Microsoft.VisualStudio.Package.ViewFilter> přijímá třídy <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> příkaz, volání třídy <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metodu parse důvod <xref:Microsoft.VisualStudio.Package.ParseReason> a umístění v době blikající kurzor <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> se odeslal příkaz. <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> Metoda analyzátor musí pak parsovat zdroje do daného umístění a potom parsovat identifikátor v daném umístění. Chcete-li zjistit, co se má zobrazit v popisu tlačítka rychlé informace.

 Většina analyzátory provést počáteční analýzy celého zdrojového souboru a výsledky uložíme v strom analýzy. Dokončení analýzy provádí při <xref:Microsoft.VisualStudio.Package.ParseReason> je předán <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metody. Jiné druhy analýzy pak můžete použít na strom analýzy získat požadované informace.

 Například analýzy z důvodu hodnotu <xref:Microsoft.VisualStudio.Package.ParseReason> můžete najít identifikátor v umístění zdroje a vyhledat ve stromu analýzy k získání informací o typu. Informace o tomto typu je pak předán <xref:Microsoft.VisualStudio.Package.AuthoringScope> třídy a je vrácený <xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDataTipText%2A> metoda.