---
title: 'DA0503: Průměr pracovní sady v bajtech pro profilovaný proces | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.503
- vs.performance.DA0503
- vs.performance.rules.DA0503
ms.assetid: 9047a494-eaaf-4679-b422-c64e8bde77a4
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b45725c59cb18f965ba7d1fa134de739d9c4144d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68205922"
---
# <a name="da0503-average-working-set-in-bytes-for-the-process-being-profiled"></a>DA0503: Průměrná pracovní sada v bajtech profilovaného procesu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Id pravidla | DA0503 |  
| Kategorie | Sledování prostředků |  
| Metoda profilace | Všechny |  
| Zpráva | Tato informace byla shromážděna pouze pro informaci. Čítač pracovní sady procesu měří využití fyzické paměti procesem, který profilujete. Hlášená hodnota je průměr vypočítaný přes všechny intervaly měření. |  
| Typ pravidla | Informace |  
  
 Při profilování pomocí vzorkování, paměti .NET nebo metodám sporu prostředků, musíte shromáždit minimálně 10 vzorky k aktivaci tohoto pravidla.  
  
## <a name="rule-description"></a>Popis pravidla  
 Tato zpráva znamená Průměrná velikost fyzické paměti, který právě používá procesu v bajtech (pracovní sady). Pracovní sada procesu představuje stránek z adresního prostoru procesu, která jsou aktuálně umístěny ve fyzické paměti.  
  
 Hlášená hodnota obsahuje rezidenční stránky ze segmentu sdílené paměti, které odkazoval na proces. Odkazy procesu obsažené v příslušných segmentech sdílené paměti, které jsou započteny sdílené knihovny DLL. Hodnota pracovní sady procesu může být vyšší než velikost virtuální paměti, která byla přidělena procesu a z důvodu sdílené paměti segmenty.  
  
 Hlášená hodnota je průměrem přes všechny intervaly měření, ve kterých byl aktivní profilovaný proces.  
  
 Velikost pracovní sady procesu odráží kolik virtuální paměti aktivně je využívána procesem. Je také vliv na množství fyzické paměti (nebo paměti RAM) k dispozici ke spuštění aplikace a množství kolizí pro tuto fyzickou paměť z jiných spuštěné procesy. Pokud je omezena fyzické paměti, je hodnota pracovní sady procesu apt výrazně jako operačních systémů liší pokusí vyrovnávat aktivní procesy využití paměti pravidelně ořízne poměrně neaktivní stránky z pracovní sady procesu.  
  
 Další informace o pracovní sady procesu najdete v tématu [pracovní sady](http://go.microsoft.com/fwlink/?LinkId=177830) v dokumentaci k Windows Správa paměti MSDN.  
  
## <a name="how-to-use-rule-data"></a>Jak používat Data pravidla  
 Použijte hodnotu pravidla pro porovnání výkonu různých verzí nebo sestavení tohoto programu nebo porozumět výkonu aplikace v různých scénářích profilování.  
  
 Dvakrát klikněte na zprávu v okně Seznam chyb, přejděte [zobrazení značky](../profiling/marks-view.md) zobrazení dat profilování. Najít **Process\Working nastavit** a **Paměť\Stránky/s** sloupce. Porovnat dva sloupce a určí, jestli je konkrétní fázích provádění programu, které se zobrazí přiřazené ke zvýšení aktivity vstupně-výstupní operace stránkování.
