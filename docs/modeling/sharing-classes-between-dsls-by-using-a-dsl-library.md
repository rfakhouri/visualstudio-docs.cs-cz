---
title: "Sdílení třídy mezi DSL, linky pomocí knihovny DSL | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: a58726bdc4e6e139963ae8cca2d12f26e0696246
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="sharing-classes-between-dsls-by-using-a-dsl-library"></a>Sdílení tříd mezi DSL pomocí knihovny DSL
V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vizualizace a modelování SDK, můžete vytvořit nekompletní definice DSL, který můžete importovat do jiné DSL. Díky tomu můžete zohlednit běžné částí podobné modelů.  
  
## <a name="creating-and-using-dsl-libraries"></a>Vytváření a používání knihovny DSL  
  
#### <a name="to-create-a-dsl-library"></a>Chcete-li vytvořit knihovnu DSL  
  
1.  Vytvoření nového projektu DSL a zvolte šablonu řešení DSL knihovny.  
  
     Vytvoří se jeden projekt DSL s prázdný model.  
  
2.  Můžete přidat třídy domény, vztahy, tvarů a tak dále.  
  
     Elementy v knihovně nemají k vytvoření jediného vnoření stromu.  
  
     Pokud chcete definovat vztah, který Importers k účetnictví můžete použít, vytvořte dvě třídy domény a vytvořit relaci mezi nimi.  
  
     Zvažte nastavení **dědičnosti modifikátor** z domény třídy `Abstract`.  
  
3.  Můžete přidat prvky, které definujete v Průzkumníku DSL, jako je připojení počítačů.  
  
4.  Můžete přidat vlastní nastavení, které vyžadují další kód, jako je například omezení ověřování.  
  
5.  Klikněte na tlačítko **proveďte transformaci všech šablon**.  
  
6.  Sestavte projekt.  
  
7.  Když distribuujete DSL pro ostatním používat, je nutné zadat kompilované sestavení (DLL) a soubor `DslDefinition.dsl`. Kompilované sestavení můžete najít ve složce v části`Dsl\bin\*`  
  
#### <a name="to-import-a-dsl-library"></a>Chcete-li importovat knihovnu DSL  
  
1.  V jiné definici DSL v **DSL Explorer**, klikněte pravým tlačítkem na třídu kořenové DSL a pak klikněte na tlačítko **přidat nové DslLibrary Import**.  
  
2.  V okně vlastnosti nastavit **cesta k souboru** knihovny. Můžete buď relativní nebo absolutní cesta.  
  
     Importované knihovny se zobrazí v Průzkumníku DSL v režimu jen pro čtení.  
  
3.  Importované třídy můžete použít jako základní třídy. Vytvořte třídu domény v import DSL a ve vlastnostech nastavte **základní třída** importované třídy.  
  
4.  Klikněte na tlačítko proveďte transformaci všech šablon.  
  
5.  Přidejte do projektu DSL odkaz na sestavení (DLL), který byl vytvořený projekt DSL knihovny.  
  
6.  Sestavte řešení.  
  
 Knihovna DSL můžete importovat další knihovny. Při importu do knihovny, jeho importy také automaticky zobrazí v Průzkumníku DSL.  
  
## <a name="see-also"></a>Viz také  
 [Jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md)
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
