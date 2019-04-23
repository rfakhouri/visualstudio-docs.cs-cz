---
title: Sdílení tříd mezi DSL pomocí knihovny DSL | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 509bd96b-3e66-47f4-8642-771421d0d0d5
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1f5b12dce533aa03cf12efd8a6f9fc26ce990e5d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60073823"
---
# <a name="sharing-classes-between-dsls-by-using-a-dsl-library"></a>Sdílení tříd mezi DSL pomocí knihovny DSL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Visualization and Modeling SDK, můžete vytvořit nekompletní definice DSL, který můžete importovat do jiného DSL. Díky tomu můžete zvážit společné části podobné modelů.  
  
## <a name="creating-and-using-dsl-libraries"></a>Vytvoření a použití knihovny DSL  
  
#### <a name="to-create-a-dsl-library"></a>Chcete-li vytvořit knihovny DSL  
  
1. Vytvoření nového projektu DSL a výběr šablony řešení knihovny DSL.  
  
     Jednoho projektu DSL se vytvoří s prázdnou modelu.  
  
2. Přidáte doménovými třídami, relace, tvary a tak dále.  
  
     Není potřeba tvoří jeden strom vkládání prvků do knihovny.  
  
     Chcete-li definovat relace, které můžete použít importers, vytvořit dvěma doménovými třídami a vytvoření relace mezi nimi.  
  
     Zvažte nastavení **modifikátor dědičnosti** doménové třídy k `Abstract`.  
  
3. Můžete přidat prvky, které definujete v Průzkumník DSL, jako je například tvůrci připojení.  
  
4. Můžete přidat vlastní nastavení, které vyžadují další kód, jako je například omezení ověření.  
  
5. Klikněte na tlačítko **Transformovat všechny šablony**.  
  
6. Sestavte projekt.  
  
7. Když distribuujete DSL pro používání jiným lidem, je nutné zadat zkompilovaného sestavení (knihovny DLL) a soubor `DslDefinition.dsl`. Můžete najít kompilované sestavení v rámci `Dsl\bin\*`  
  
#### <a name="to-import-a-dsl-library"></a>Postup importování knihovny DSL  
  
1. V jiné definici DSL v **Průzkumník DSL**, klikněte pravým tlačítkem na kořenová třída DSL a potom klikněte na tlačítko **přidejte Import nového knihovny DSL**.  
  
2. V okně Vlastnosti nastavte **cesta k souboru** knihovny. Můžete použít relativní nebo absolutní cesta.  
  
    Importovanou knihovnu se zobrazí v Průzkumníku DSL v režimu jen pro čtení.  
  
3. Importované třídy lze použít jako základní třídy. Vytvoření doménové třídy v importu DSL a ve vlastnostech okno, nastavte **základní třída** importované třídy.  
  
4. Klikněte na tlačítko Transformovat všechny šablony.  
  
5. Přidáte do projektu DSL odkaz na sestavení (DLL), který byl vytvořen projekt knihovny DSL.  
  
6. Sestavte řešení.  
  
   Knihovna DSL, která můžete importovat další knihovny. Při importu knihovny jeho importů také automaticky zobrazí v Průzkumníku DSL.  
  
## <a name="see-also"></a>Viz také  
 [Jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md)
