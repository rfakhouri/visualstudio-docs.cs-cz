---
title: "Více DSL, linky v jednom řešení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e668620-6217-4e87-aea7-e9036776c8e4
caps.latest.revision: "3"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: b55d1d5ec8e84c8d16681ffd0ac738291e1bc39d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="multiple-dsls-in-one-solution"></a>Vícesouborové DSL v jediném řešení
V rámci jedné řešení můžete balíček několik DSL, linky, tak, že jsou nainstalovány společně.  
  
 Můžete použít několik postupů k integraci více DSL, linky. Další informace najdete v tématu [integrace modelů pomocí Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md) a [postupy: přidání obslužné rutiny a přetažení](../modeling/how-to-add-a-drag-and-drop-handler.md) a [přizpůsobení chování kopie](../modeling/customizing-copy-behavior.md).  
  
### <a name="to-build-more-than-one-dsl-in-the-same-solution"></a>K vytvoření více než jeden DSL ve stejném řešení  
  
1.  Vytvoření dvou nebo více DSL řešení a projektu VSIX a přidejte všechny projekty do jednoho řešení.  
  
    -   K vytvoření nového projektu VSIX: V **nový projekt** dialogovém okně, vyberte **Visual C#**, **rozšiřitelnost**, **projektu VSIX**.  
  
    -   Vytvoření dvou nebo více DSL řešení v adresáři řešení VSIX.  
  
         Pro každý DSL otevřete novou instanci sady Visual Studio. Vytvořte nový DSL a zadejte stejné složce řešení jako řešení VSIX.  
  
         Zajistěte, aby vytvoříte každý DSL s příponou jiný název souboru.  
  
    -   Změna názvů **Dsl** a **DslPackage** projekty, aby byly všechny různé. Příklad: `Dsl1`, `DslPackage1`, `Dsl2`, `DslPackage2`.  
  
    -   V každé **DslPackage\*\source.extension.tt**, aktualizovat tohoto řádku na správný název projektu Dsl:  
  
         `string dslProjectName = "Dsl2";`  
  
    -   V řešení VSIX přidejte Dsl * a DslPackage\* projekty.  
  
         Můžete chtít umístit každý pár v jeho vlastní řešení.  
  
2.  Kombinování VSIX manifesty DSL, linky:  
  
    1.  Otevřete *YourVsixProject***\source.extension.manifest**.  
  
    2.  Pro každý DSL, zvolte **přidat obsahu** a přidejte:  
  
        -   `Dsl*`projekt jako **Komponenta MEF**  
  
        -   `DslPackage*`projekt jako **Komponenta MEF**  
  
        -   `DslPackage*`projekt jako **balíčku VS**  
  
3.  Sestavte řešení.  
  
 Výsledný VSIX nainstaluje i DSL, linky. Můžete otestovat pomocí F5 nebo nasazení *YourVsixProject***\bin\Debug\\\*VSIX**.  
  
## <a name="see-also"></a>Viz také  
 [Integrace modelů pomocí Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md)   
 [Postupy: přidání obslužné rutiny a přetažení](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Kopírování chování přizpůsobení](../modeling/customizing-copy-behavior.md)