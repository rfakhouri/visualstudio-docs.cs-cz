---
title: "Postupy: povolení a zákaz úplnou analýzu řešení pro spravovaný kód | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- full solution analysis
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-code-analysis
ms.workload:
- dotnet
ms.openlocfilehash: 64b541093aaf1a710976c0f53a3214b5d2a47e0d
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-enable-and-disable-full-solution-analysis-for-managed-code"></a>Postupy: povolení a zákaz úplnou analýzu řešení pro spravovaný kód

*Úplné řešení analysis* je funkce sady Visual Studio, který vám umožní vidět problémy pouze v otevřených souborů Visual C# nebo Visual Basic v řešení pro analýzu kódu, nebo také v kódu soubory, které jsou uzavřeny. Ve výchozím nastavení úplnou analýzu řešení povoleno jazyka Visual Basic a zakázáno pro Visual C#.

Když se moci zobrazit všechny problémy v všechny soubory je užitečné, může být rušivě. Je také možné pomalé Visual Studio dolů Pokud vaše řešení je velký nebo obsahuje mnoho souborů. Chcete-li omezit počet problémů zobrazí a zlepšit výkon v sadě Visual Studio, můžete zakázat úplnou analýzu řešení. V případě potřeby můžete snadno znovu povolit tuto funkci.

## <a name="to-toggle-full-solution-analysis"></a>K přepnutí úplnou analýzu řešení

1. Chcete-li otevřít **možnosti** dialogové okno, v řádku nabídek v sadě Visual Studio zvolte **nástroje** > **možnosti**.

1. V **možnosti** dialogovém okně vyberte **textového editoru** > **C#** nebo **základní**  >   **Rozšířené**.

1. Vyberte **povolit úplnou analýzu řešení** zaškrtněte políčko Povolit úplnou analýzu řešení, nebo zrušte zaškrtnutí políčka ji zakázat. Vyberte **OK** tlačítko po dokončení.

    ![Povolte úplnou řešení analysis zaškrtávací políčko. ] (../code-quality/media/fsa_toolsoptions.png "FSA_ToolsOptions")

## <a name="results-of-enabling-and-disabling-full-solution-analysis"></a>Výsledky povolování a zakazování úplnou analýzu řešení

Na následujícím snímku obrazovky uvidíte výsledky, pokud je povoleno úplnou analýzu řešení. Všechny chyby a problémy v analýzy kódu *všechny* souborů v řešení se zobrazí, bez ohledu na to, jestli jsou soubory otevřené nebo ne.

![Úplnou analýzu řešení povoleno. ] (../code-quality/media/fsa_enabled.png "FSA_Enabled")

Následující snímek obrazovky ukazuje výsledky ze stejného řešení po zakázání úplnou analýzu řešení. Pouze chyby a problémy v analýzy kódu otevřete řešení, které soubory se zobrazí v seznamu chyb.

![Úplnou analýzu řešení zakázána. ] (../code-quality/media/fsa_disabled.png "FSA_Disabled")

## <a name="automatically-disabling-full-solution-analysis"></a>Automatickým zakázáním úplnou analýzu řešení

Pokud Visual Studio rozpozná, že 200MB nebo menší systémové paměti je dostupné, se automaticky zakáže úplnou analýzu řešení (stejně jako některé další funkce) je-li aktivní. Pokud k tomu dojde, zobrazí se výstraha, která vás informuje o to. Tlačítko umožňuje v případě potřeby znovu povolit úplnou analýzu řešení.

![Pozastavení úplnou analýzu řešení textu výstrahy](../code-quality/media/fsa_alert.png "FSA_Alert")