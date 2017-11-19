---
title: "Postupy: změna mezi zápisem člena a zápisem asociace (návrhář tříd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- notation, member
- association notation
- member notation
- notation, association
ms.assetid: 65881c5a-d251-4a36-ad0d-73d088436092
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6cee0c289c67bb67213e963635334e96101ac690
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-change-between-member-notation-and-association-notation-class-designer"></a>Postupy: Změna mezi zápisem člena a zápisem asociace (návrhář tříd)
V Návrháři tříd můžete změnit způsob diagramu tříd představuje relaci přidružení mezi dvěma typy z notace členů notace přidružení a naopak. Členy zobrazené jako Asociační čáry často poskytují užitečné vizualizaci jak typy souvisejí.  
  
> [!NOTE]
>  Přidružení relace může být reprezentován jako člen vlastnost nebo pole. Chcete-li změnit notace členů notace přidružení, musí mít jeden typ členem jiného typu. Notace přidružení změnit na notace členů, existují dva typy musí být připojen přidružení čára. Další informace najdete v tématu [postupy: vytvoření přidružení mezi typy (návrhář tříd)](../ide/how-to-create-associations-between-types-class-designer.md). Pokud projekt obsahuje více diagramů tříd, změny, které provedete způsob diagram zobrazuje přidružení vztahy ovlivňují jenom tento diagram. Změnit způsob jiný diagram zobrazuje přidružení vztahů, otevřete nebo zobrazit tento diagram a proveďte tyto kroky.  
  
### <a name="to-change-member-notation-to-association-notation"></a>Chcete-li změnit notace členů do notace přidružení  
  
1.  Z uzlu projektu v Průzkumníku řešení otevřete soubor třídy diagram (.cd).  
  
2.  V obrazce typu v diagramu tříd, klikněte pravým tlačítkem člen vlastnost nebo pole představující přidružení a zvolte **zobrazit jako přidružení**.  
  
    > [!TIP]
    >  Pokud žádné vlastnosti nebo pole jsou viditelné v obrazce typu, mohou být sbaleny přihrádky ve tvaru. Rozšířit obrazce typu, klikněte dvakrát na název prostředí nebo klikněte pravým tlačítkem na obrazce typu a vyberte **rozbalte**.  
  
     Člen dané zařízení zmizí z prostředí v obrazce typu a řádku s přidružení se zobrazí oba typy připojení. Přidružení řádek označený verzí název vlastnost nebo pole.  
  
### <a name="to-change-association-notation-to-member-notation"></a>Chcete-li změnit notace přidružení k notace členů  
  
-   Na diagramu tříd, klikněte pravým tlačítkem na ose přidružení a zvolte **zobrazit jako vlastnost** nebo **zobrazit jako pole** podle potřeby.  
  
     Přidružení řádku zmizí, a vlastnost zobrazí v příslušné prostředí v rámci jeho obrazce typu v diagramu.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření dědičnosti mezi typy (návrhář tříd)](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [Postupy: zobrazení dědičnosti mezi typy (návrhář tříd)](../ide/how-to-view-inheritance-between-types-class-designer.md)   
 [Zobrazování typů a vztahů (návrhář tříd)](../ide/viewing-types-and-relationships-class-designer.md)   
 [Postupy: vizualizace asociace kolekce (návrhář tříd)](../ide/how-to-visualize-a-collection-association-class-designer.md)