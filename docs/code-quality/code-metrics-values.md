---
title: "Hodnoty metrik kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code metrics
- code analysis
- measure code quality
ms.assetid: bc38831e-2083-4ea4-8527-ee41499a342f
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 234ec06d47afee3cbde7c2333742fe43ab599219
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="code-metrics-values"></a>Hodnoty metrik kódu
Metriky kódu je sada míry softwaru, které poskytují vývojářům lepší přehled o kód, že jejich vývoj. Využitím metriky kódu, můžete vývojáři pochopit, jaké typy a metody by měla být přepracována nebo více důkladně neotestovali. Vývojové týmy můžete zjistit potenciální rizika, informace o aktuálním stavu projektu a sledovat průběh během vývoje softwaru.  
  
## <a name="software-measurements"></a>Měření softwaru  
 V následujícím seznamu jsou výsledky metrik kódu, který [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vypočítá:  
  
-   **Index udržovatelnosti** -vypočítá index hodnotu mezi 0 a 100 představující relativně snadno Správa kód. Vysoká hodnota znamená vyšší udržovatelnosti. Hodnocení barevně lze rychle identifikovat problémová místa v kódu. Zelená hodnocení je 20 až 100 a znamená, že kód má dobrou udržovatelnosti. Žlutý hodnocení je 10 až 19 a označuje, že je kód mírně udržovatelný. Red hodnocení je hodnocení 0 až 9 a Určuje nízkou udržovatelnosti.  
  
-   **Složitost Cyclomatic** -měří strukturální složitost kódu. Je vytvořen pomocí výpočtu počet cesty jiný kód v toku programu. Program, který obsahuje komplexní řízení toku bude vyžadovat další testy k dosažení pokrytí dobrý kódu a bude menší udržovatelný.  
  
    > [!NOTE]
    >  V některých případech výpočtu složitost cyclomatic pro metodu v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] se liší od předchozích verzí. Další informace najdete v tématu "Změny ve Visual Studio 2010 kód složitost výpočty části" z [řešení potíží s problémy metriky kódu](../code-quality/troubleshooting-code-metrics-issues.md).  
  
-   **Hloubka dědičnosti** -určuje počet definice tříd, které rozšiřují se s kořenem hierarchie tříd. Čím hlouběji hierarchii obtížnější může být zjistit, kde jsou definovány konkrétní metody a pole nebo / a Předefinovaná.  
  
-   **Třídy párování** -měří párování na jedinečný třídy prostřednictvím parametry, místní proměnné, návratové typy, volání metod, konkretizací obecného nebo šablony, základní třídy, implementace rozhraní, pole definovaná v externí typy a dekorace atribut. Návrh dobrý softwaru stanoví, že typy a metody by měla mít vysokou soudržnost a nízká spojovacích. Vysoká párování označuje návrhu, které je obtížné opakovaně používat a udržovat z důvodu jeho mnoho vzájemné závislosti na jiné typy.  
  
-   **Řádky kódu** -určuje přibližný počet řádků v kódu. Počet je založený na kód IL a není proto přesný počet řádků v souboru se zdrojovým kódem. Velmi vysoký počet může znamenat, že typ nebo metoda se pokouší příliš mnoho práci a má dělit. Také může znamenat, že typ nebo metoda může být obtížné spravovat.  
  
## <a name="anonymous-methods"></a>Anonymní metody  
 *Anonymní metoda* je právě metoda, která nemá žádný název. Anonymní metody jsou nejčastěji sloužící k předávání blok kódu jako parametr delegáta. Výsledky metrik pro anonymní metodu, která je deklarován v členem, jako je metoda nebo přistupující objekt, jsou přidruženy k člena, který deklaruje metodu. Nejsou přidruženy člena, který volá metodu.  
  
 Další informace o způsobu metriky kódu s anonymní metody najdete v tématu [anonymní metody a analýza kódu](../code-quality/anonymous-methods-and-code-analysis.md).  
  
## <a name="generated-code"></a>Generovaný kód  
 Některé softwarové nástroje a kompilátory generování kódu, který se přidá do projektu a že vývojář projektu nezná nebo neměli měnit. Metriky kódu nejčastěji, ignoruje generovaného kódu při výpočtu hodnoty metrik. To umožňuje hodnoty metrik tak, aby odrážela co může vývojář zobrazit a měnit.  
  
 Kód generovaný pro Windows forms není ignorován, protože je kód, který vývojář může zobrazit a měnit.  
  
## <a name="see-also"></a>Viz také  
 [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)