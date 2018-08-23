---
title: Vícesouborové DSL v jediném řešení | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e668620-6217-4e87-aea7-e9036776c8e4
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: fe0d7877a68c34cd624d20834f553e9ec18d1df2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668557"
---
# <a name="multiple-dsls-in-one-solution"></a>Vícesouborové DSL v jediném řešení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vícesouborové DSL v jediném řešení](https://docs.microsoft.com/visualstudio/modeling/multiple-dsls-in-one-solution).  
  
Jako součást jediného řešení můžete zabalit několik DSL, tak, že jsou nainstalovány společně.  
  
 Můžete použít několik technik k integraci vícesouborové DSL. Další informace najdete v tématu [integrace modelů pomocí Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md) a [postupy: přidání obslužné rutiny operace přetažení myší](../modeling/how-to-add-a-drag-and-drop-handler.md) a [přizpůsobení chování kopírování](../modeling/customizing-copy-behavior.md).  
  
### <a name="to-build-more-than-one-dsl-in-the-same-solution"></a>K vytvoření více než jednom DSL ve stejném řešení  
  
1.  Vytvořte dvě nebo více řešení DSL a projekt VSIX a přidejte všechny projekty do jediného řešení.  
  
    -   Chcete-li vytvořit nový projekt VSIX: V **nový projekt** dialogového okna, vyberte **Visual C#**, **rozšiřitelnost**, **projekt VSIX**.  
  
    -   Vytvoření dvou nebo více řešení DSL v adresáři řešení VSIX.  
  
         Pro každý DSL otevřete novou instanci sady Visual Studio. Vytvořte nový DSL a zadejte stejnou složku řešení jako řešení VSIX.  
  
         Ujistěte se, že vytvoření každé DSL s příponou jiný název souboru.  
  
    -   Změna názvů **Dsl** a **DslPackage** projekty tak, aby byly všechny různé. Příklad: `Dsl1`, `DslPackage1`, `Dsl2`, `DslPackage2`.  
  
    -   V každém **DslPackage\*\source.extension.tt**, aktualizujte tohoto řádku na správný název projektu Dsl:  
  
         `string dslProjectName = "Dsl2";`  
  
    -   Do řešení VSIX, přidejte Dsl * a DslPackage\* projekty.  
  
         Můžete chtít umístit každý pár ve vlastní složce řešení.  
  
2.  Kombinovat manifestu VSIX DSL:  
  
    1.  Open *YourVsixProject***\source.extension.manifest**.  
  
    2.  Pro každý DSL, zvolte **přidat obsah** a přidejte:  
  
        -   `Dsl*` projekt jako **Komponenta MEF**  
  
        -   `DslPackage*` projekt jako **Komponenta MEF**  
  
        -   `DslPackage*` projekt jako **balíček VS**  
  
3.  Sestavte řešení.  
  
 Výsledný VSIX nainstaluje i DSL. Můžete otestovat pomocí klávesy F5 nebo nasazení * YourVsixProject ***\bin\Debug\\\*VSIX**.  
  
## <a name="see-also"></a>Viz také  
 [Integrace modelů pomocí Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md)   
 [Postupy: přidání obslužné rutiny operace přetažení myší](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Přizpůsobení chování kopírování](../modeling/customizing-copy-behavior.md)



