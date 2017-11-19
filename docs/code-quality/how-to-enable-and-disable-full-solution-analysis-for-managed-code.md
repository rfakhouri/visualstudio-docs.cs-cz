---
title: "Postupy: povolení a zákaz úplnou analýzu řešení pro spravovaný kód | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: full solution analysis
ms.assetid: 04315147-5792-47f0-8b5f-9ac8413c6a57
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-code-analysis
ms.openlocfilehash: 94cda949a713a773e5586e5b1ef284c6ba54839c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-enable-and-disable-full-solution-analysis-for-managed-code"></a>Postupy: povolení a zákaz úplnou analýzu řešení pro spravovaný kód
> [!NOTE]
>  Toto téma se vztahuje pouze k Visual Studio 2015 Update 3 RC a novějším.  
  
 *Úplné řešení analysis* je funkce sady Visual Studio, který můžete zvolit, zda se zobrazí problémy analýzy kódu jenom v otevřených Visual C# nebo Visual Basic souborů ve vašem řešení, nebo v otevřené a uzavřené Visual C# nebo Visual Basic soubory ve vašem řešení.  
  
 Když se moci zobrazit všechny problémy v všechny soubory je užitečné, může být rušivě a i zpomalit Visual Studio Pokud vaše řešení je velký nebo obsahuje mnoho souborů.  Chcete-li omezit počet problémů zobrazí a zlepšit výkon v sadě Visual Studio, můžete zakázat úplnou analýzu řešení. Pokud chcete, můžete snadno znovu povolit tuto funkci.  
  
#### <a name="to-toggle-full-solution-analysis"></a>K přepnutí úplnou analýzu řešení  
  
1.  Na hlavní nabídky v sadě Visual Studio, zvolte **nástroje** &#124; **Možnosti** zobrazíte **možnosti** dialogové okno.  
  
2.  V **možnosti** dialogovém okně vyberte **textového editoru** &#124; **C#** nebo **základní** &#124; **Rozšířené**.  
  
3.  Vyberte **povolit úplnou analýzu řešení** zaškrtněte políčko Povolit úplnou analýzu řešení, nebo zrušte zaškrtnutí políčka ji zakázat. Vyberte **OK** tlačítko po dokončení.  
  
     ![Povolte úplnou řešení analysis zaškrtávací políčko. ] (../code-quality/media/fsa_toolsoptions.png "FSA_ToolsOptions")  
  
## <a name="results-of-enabling-and-disabling-full-solution-analysis"></a>Výsledky povolování a zakazování úplnou analýzu řešení  
 Na následujícím snímku obrazovky uvidíte výsledky, pokud je povoleno úplnou analýzu řešení. Všechny chyby a problémy v analýzy kódu *všechny* souborů v řešení se zobrazí, bez ohledu na to, jestli jsou soubory otevřené nebo ne.  
  
 ![Úplnou analýzu řešení povoleno. ] (../code-quality/media/fsa_enabled.png "FSA_Enabled")  
  
 Následující snímek obrazovky ukazuje výsledky ze stejného řešení po zakázání úplnou analýzu řešení. Pouze chyby a problémy v analýzy kódu otevřete řešení, které soubory se zobrazí v seznamu chyb.  
  
 ![Úplnou analýzu řešení zakázána. ] (../code-quality/media/fsa_disabled.png "FSA_Disabled")  
  
## <a name="automatically-disabling-full-solution-analysis"></a>Automatickým zakázáním úplnou analýzu řešení  
 Pokud Visual Studio rozpozná, že 200MB nebo menší systémové paměti je dostupné, se automaticky zakáže úplnou analýzu řešení (stejně jako některé další funkce) je-li aktivní. Pokud k tomu dojde, zobrazí se výstraha, která vás informuje o to. Tlačítko umožňuje znovu povolit úplnou analýzu řešení, pokud chcete udělat.  
  
 ![Pozastavení úplnou analýzu řešení textu výstrahy](../code-quality/media/fsa_alert.png "FSA_Alert")  
  
## <a name="additional-details"></a>Další podrobnosti  
 Ve výchozím nastavení úplnou analýzu řešení povoleno jazyka Visual Basic a zakázáno pro Visual C#.  
  
 Visual Studio Update 3 RC zahrnuje rozšířené kód analyzátor diagnostiky v2 modul, který výrazně snižuje využití paměti a snižuje doba využití procesoru při nečinnosti, i když je povolená úplnou analýzu řešení.