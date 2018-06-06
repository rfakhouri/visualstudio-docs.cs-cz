---
title: 'DA0017: Vysoké míry stránkování aktivní paměti na disk | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.17
- vs.performance.rules.DA0017
- vs.performance.DA0017
ms.assetid: 01011eec-5930-43b3-980d-2cb01e2ca7f6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 60dfbba96a7b52ff271e1633528cf0934e347b6e
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749840"
---
# <a name="da0017-high-rates-of-paging-active-memory-to-disk"></a>DA0017: Vysoké míry stránkování aktivní paměti na disk
|||  
|-|-|  
|Id pravidla|DA0017|  
|Kategorie|Paměti a stránkování|  
|Metoda profilace|Všechny|  
|Zpráva|Dochází k vysoké míry stránkování aktivní paměti na disk. Aplikace může být vázané na paměť.|  
|Typ pravidla|Informace o|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Data výkonu systému, která nebyla shromážděna v profilaci spustit označuje, že vysoké míry stránkování aktivní paměti na a z disku došlo k chybě v průběhu vytváření profilů spustit. Stránkování sazby na této úrovni normálně ovlivní výkon aplikace a odezvy. Zvažte snížení přidělení paměti prostřednictvím revize algoritmy. Budete také muset zvažte požadavky na paměť vaší aplikace.  
  
## <a name="rule-description"></a>Popis pravidla  
  
> [!NOTE]
>  Toto pravidlo informační aktivuje se v případě dosažení značné množství úrovně stránkování aktivní paměti. Pokud dojde k velmi vysoký stupeň stránkování, pravidlo upozornění [DA0014: velmi vysoké míry stránkování aktivní paměti na disk](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md) aktivuje místo.  
  
 Nadměrné stránkování na disk může být způsobeno nedostatku fyzické paměti. Pokud stránkovací operace dominujte použití fyzického disku, na které se nachází soubor stránkování, může zpomalit na stejném disku, na dalších operací zaměřené na disku.  
  
 Stránky jsou často načten z disku nebo zapíší na disk v hromadné operace stránkování. Počet výstup stránek/s je často mnohem vyšší než počet zápisů stránek/s, např. Protože výstup stránek/s je také stránky změněná data z mezipaměti systému souborů. Však není vždy snadno zjistit, které proces přímo zodpovídá za stránkování nebo proč.  
  
## <a name="how-to-fix-violations"></a>Jak opravit porušení  
 Klikněte dvakrát na zprávy v okně Seznam chyb navigaci na [značky](../profiling/marks-view.md) zobrazení. Najít **Paměť\Stránky/s** sloupce. Zjistěte, jestli konkrétní fáze spuštění programu kde aktivity vstupně-výstupní operace stránkování je větší než jiné.  
  
 Pokud se shromažďování dat profilu pro aplikaci ASP.NET do scénáře zátěžového testování, zkuste spustit znovu zátěžový test na počítači nakonfigurována s další fyzické paměti (nebo RAM).  
  
 Zvažte snížení úprava algoritmy a vyloučení rozhraní API náročné na paměť třeba String.Concat a String.Substring přidělení paměti.