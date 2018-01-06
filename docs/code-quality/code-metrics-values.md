---
title: "Vypočítat metriky kódu v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code metrics [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dc9a688892ca7ec08a89c4da8e1732b5e2b3e267
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="code-metrics-values"></a>Hodnoty metrik kódu

Zvýšená složitosti moderní softwarové aplikace se taky zvýší je obtížné zajistit kód spolehlivé a udržovatelný. Metriky kódu je sada míry softwaru, které poskytují vývojářům lepší přehled o kód, že jejich vývoj. Využitím metriky kódu, můžete vývojáři pochopit, jaké typy a metody by měla být přepracována nebo více důkladně neotestovali. Vývojové týmy můžete zjistit potenciální rizika, informace o aktuálním stavu projektu a sledovat průběh během vývoje softwaru.

Vývojářům můžete použít Visual Studio k vygenerování dat metrik kódu, který měření složitosti a udržovatelnosti jejich spravovaného kódu. Daty metrik kódu lze vygenerovat pro celé řešení nebo jeden projekt.

## <a name="software-measurements"></a>Měření softwaru

V následujícím seznamu jsou výsledky metrik kódu, který [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vypočítá:

- **Index udržovatelnosti** -vypočítá index hodnotu mezi 0 a 100 představující relativně snadno Správa kód. Vysoká hodnota znamená vyšší udržovatelnosti. Hodnocení barevně lze rychle identifikovat problémová místa v kódu. Zelená hodnocení je 20 až 100 a znamená, že kód má dobrou udržovatelnosti. Žlutý hodnocení je 10 až 19 a označuje, že je kód mírně udržovatelný. Red hodnocení je hodnocení 0 až 9 a Určuje nízkou udržovatelnosti.

- **Složitost Cyclomatic** -měří strukturální složitost kódu. Je vytvořen pomocí výpočtu počet cesty jiný kód v toku programu. Program, který obsahuje komplexní řízení toku bude vyžadovat další testy k dosažení pokrytí dobrý kódu a bude menší udržovatelný.

- **Hloubka dědičnosti** -určuje počet definice tříd, které rozšiřují se s kořenem hierarchie tříd. Čím hlouběji hierarchii obtížnější může být zjistit, kde jsou definovány konkrétní metody a pole nebo / a Předefinovaná.

- **Třídy párování** -měří párování na jedinečný třídy prostřednictvím parametry, místní proměnné, návratové typy, volání metod, konkretizací obecného nebo šablony, základní třídy, implementace rozhraní, pole definovaná v externí typy a dekorace atribut. Návrh dobrý softwaru stanoví, že typy a metody by měla mít vysokou soudržnost a nízká spojovacích. Vysoká párování označuje návrhu, které je obtížné opakovaně používat a udržovat z důvodu jeho mnoho vzájemné závislosti na jiné typy.

- **Řádky kódu** -určuje přibližný počet řádků v kódu. Počet je založený na kód IL a není proto přesný počet řádků v souboru se zdrojovým kódem. Velmi vysoký počet může znamenat, že typ nebo metoda se pokouší příliš mnoho práci a má dělit. Také může znamenat, že typ nebo metoda může být obtížné spravovat.

## <a name="anonymous-methods"></a>Anonymní metody

*Anonymní metoda* je právě metoda, která nemá žádný název. Anonymní metody jsou nejčastěji sloužící k předávání blok kódu jako parametr delegáta. Výsledky metrik pro anonymní metodu, která je deklarován v členem, jako je metoda nebo přistupující objekt, jsou přidruženy k člena, který deklaruje metodu. Nejsou přidruženy člena, který volá metodu.

Další informace o způsobu metriky kódu s anonymní metody najdete v tématu [anonymní metody a analýza kódu](../code-quality/anonymous-methods-and-code-analysis.md).

## <a name="generated-code"></a>Generovaný kód

Některé softwarové nástroje a kompilátory generování kódu, který se přidá do projektu a že vývojář projektu nezná nebo neměli měnit. Metriky kódu nejčastěji, ignoruje generovaného kódu při výpočtu hodnoty metrik. To umožňuje hodnoty metrik tak, aby odrážela co může vývojář zobrazit a měnit.

Kód generovaný pro Windows Forms není ignorován, protože je kód, který vývojář může zobrazit a měnit.