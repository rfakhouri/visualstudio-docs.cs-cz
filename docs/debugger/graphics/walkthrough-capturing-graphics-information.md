---
title: "Návod: Zaznamenání grafických informací | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48f12f6e-57b4-48ec-a145-89fa71a42424
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 11213c60eb03626f86b51f896b6edb487c3e3394
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-capturing-graphics-information"></a>Návod: Zaznamenání grafických informací
Tento návod ukazuje, jak používat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] diagnostiky grafiky k ručně zaznamenání grafických informací z aplikace Direct3D.  
  
 Tento návod ukazuje tyto úlohy:  
  
-   Zapojování diagnostiky grafiky do vaší aplikace  
  
-   Zachycení informací grafiky  
  
## <a name="capturing-graphics-information"></a>Zachycení informací grafiky  
 Při použití nástroje pro diagnostiky grafiky, musíte nejprve zaznamenání grafických informací, na kterém je závislý. Pokud chcete povolit zachycení, použijte **spustit diagnostické nástroje** příkaz napojit diagnostiky grafiky k aplikaci při spuštění.  
  
#### <a name="to-enable-the-capture-of-graphics-information-after-a-project-or-solution-is-loaded"></a>Chcete-li povolit zaznamenání grafických informací po projekt nebo řešení je načteno  
  
1.  V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], načíst soubor projekt nebo řešení pro aplikaci, kterou chcete zaznamenání grafických informací z.  
  
2.  Na panelu nástrojů diagnostiky grafiky zvolte **spustit diagnostické nástroje**.  
  
#### <a name="to-enable-the-capture-of-graphics-information-without-loading-a-project-or-solution"></a>Chcete-li povolit zaznamenání grafických informací bez načítání projekt nebo řešení  
  
1.  Na řádku nabídek zvolte **soubor**, **otevřete**, **projekt nebo řešení**. **Otevřeného projektu** zobrazí se dialogové okno.  
  
2.  Místo souboru projekt nebo řešení, zadejte spustitelný soubor pro aplikaci, kterou chcete zaznamenání grafických informací z a potom vyberte **otevřete**.  
  
3.  Na řádku nabídek zvolte **ladění**, **grafiky**, **spustit diagnostické nástroje**.  
  
 Po spuštění aplikace a je vykreslování rámce, můžete zachytit grafických informací.  
  
#### <a name="to-capture-graphics-information"></a>K zaznamenání grafických informací  
  
-   Na panelu nástrojů diagnostiky grafiky, vyberte **zaznamenat** tlačítko. ![Grafika zaznamenat tlačítko ikonu](media/debuggingdirectxgraphics.png "DebuggingDirectXGraphics")  
  
     -nebo-  
  
     S aplikací v fokus, stiskněte klávesu **Print Screen**.  
  
 Při každém zaznamenání informací o rámce, diagnostiky grafiky zaznamenává Direct3D – události a přidružený stav a přidá tato data do protokolu grafiky. Pro každou relaci diagnostiky grafiky je vytvořen nový protokol grafiky. Informace o grafických protokolů najdete v tématu [přehled](overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukázal, jak k zaznamenání grafických informací ručně. Jako další krok vezměte v úvahu tuto možnost:  
  
-   Zjistěte, jak analyzovat zaznamenané grafických informací pomocí diagnostiky grafiky nástrojů. V tématu [přehled](overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>Viz také  
 [Zaznamenání grafických informací](capturing-graphics-information.md)