---
title: "DA0014: Velmi vysoké míry stránkování aktivní paměti na disk | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DAMemoryBound
- vs.performance.DA0014
- vs.performance.14
- vs.performance.rules.DA0014
ms.assetid: a7fa3749-9191-437a-9331-9d917181e62f
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 039e117d9a5ce4741e637d5daa95be18091554b0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0014-extremely-high-rates-of-paging-active-memory-to-disk"></a>DA0014: Velmi vysoké míry stránkování aktivní paměti na disk
|||  
|-|-|  
|Id pravidla|DA0014|  
|Kategorie|Paměti a stránkování|  
|Metoda profilace|Všechny|  
|Zpráva|Dochází velmi vysoké míry stránkování aktivní paměti na disk. Aplikace může být vázané na paměť.|  
|Typ pravidla|Upozornění|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 25 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 Data výkonu systému, která nebyla shromážděna v profilaci spustit označuje, že velmi vysoké míry stránkování aktivní paměti na a z disku došlo k chybě v průběhu vytváření profilů spustit. Obvykle stránkování sazby na této úrovni má dopad na výkon aplikace a odezvy. Zvažte snížení přidělení paměti prostřednictvím revize algoritmy. Budete také muset zvažte požadavky na paměť vaší aplikace. spuštění profilace znovu na počítači s více paměti.  
  
## <a name="rule-description"></a>Popis pravidla  
 Nadměrné stránkování na disk může být způsobeno nedostatku fyzické paměti. Pokud stránkovací operace dominujte použití fyzického disku, na které se nachází soubor stránkování, může zpomalit na stejném disku, na dalších operací zaměřené na disku.  
  
 Stránky jsou často, čtení z disku nebo zapíší na disk v hromadné operace stránkování. Počet výstup stránek/s je často mnohem vyšší než počet zápisů stránek/s, například. Protože výstup stránek/s je také stránky změněná data z mezipaměti systému souborů. Však není vždy snadno zjistit, které proces přímo zodpovídá za stránkování nebo proč.  
  
> [!NOTE]
>  Toto pravidlo aktivuje se v případě dosažení úrovně stránkování aktivní paměti na velmi vysokou míru. Informační pravidlo, pokud je úroveň stránkování významné, ale není extrémně [DA0017: vysoké míry stránkování aktivní paměti na disk](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md) aktivuje místo.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Klikněte dvakrát na zprávy v okně Seznam chyb navigaci na [značky](../profiling/marks-view.md) zobrazení. Najít **Paměť\Stránky/s** sloupce. Zjistěte, jestli konkrétní fáze spuštění programu kde aktivity vstupně-výstupní operace stránkování je větší než jiné.  
  
 Pokud se shromažďování dat profilu pro aplikaci ASP.NET do scénáře zátěžového testování, zkuste spustit znovu zátěžový test na počítači nakonfigurována s další fyzické paměti (nebo RAM).  
  
 Zvažte snížení úprava algoritmy a vyloučení rozhraní API náročné na paměť třeba String.Concat a String.Substring přidělení paměti.