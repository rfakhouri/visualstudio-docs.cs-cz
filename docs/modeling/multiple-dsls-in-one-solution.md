---
title: "Více DSL, linky v jednom řešení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f3c024fc6be841f5329f133ece35ed0ef7517eb3
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
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
  
    1.  Otevřete * YourVsixProject ***\source.extension.manifest**.  
  
    2.  Pro každý DSL, zvolte **přidat obsahu** a přidejte:  
  
        -   `Dsl*`projekt jako **Komponenta MEF**  
  
        -   `DslPackage*`projekt jako **Komponenta MEF**  
  
        -   `DslPackage*`projekt jako **balíčku VS**  
  
3.  Sestavte řešení.  
  
 Výsledný VSIX nainstaluje i DSL, linky. Můžete otestovat pomocí F5 nebo nasazení * YourVsixProject ***\bin\Debug\\\*VSIX**.  
  
## <a name="see-also"></a>Viz také  
 [Integrace modelů pomocí Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md)   
 [Postupy: přidání obslužné rutiny a přetažení](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Přizpůsobení chování kopírování](../modeling/customizing-copy-behavior.md)