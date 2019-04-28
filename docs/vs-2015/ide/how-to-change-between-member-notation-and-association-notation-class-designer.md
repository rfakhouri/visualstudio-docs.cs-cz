---
title: 'Postupy: Změna mezi zápisem člena a zápisem asociace (návrhář tříd) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- notation, member
- association notation
- member notation
- notation, association
ms.assetid: 65881c5a-d251-4a36-ad0d-73d088436092
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2c0e691cd162a52dc598f9d3dc4d9a04e0f8f008
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63439297"
---
# <a name="how-to-change-between-member-notation-and-association-notation-class-designer"></a>Postupy: Změna mezi zápisem člena a zápisem asociace (návrhář tříd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V Návrháři tříd můžete změnit způsob, jakým diagram tříd reprezentuje vztah přidružení mezi dvěma typy z zápisem člena zápisem asociace a naopak. Členové zobrazí jako Asociační čáry často poskytují užitečné vizualizace z jak související typy.  
  
> [!NOTE]
> Přidružení relace může být reprezentována jako člen vlastnost nebo pole. Chcete-li změnit zápisem člena pro zápisem asociace, musí mít jeden typ členem jiného typu. Chcete-li změnit zápisem asociace na zápisem člena, musí být připojen dva typy systémem Asociační čára. Další informace najdete v tématu [jak: Vytvoření asociací mezi typy (návrhář tříd)](../ide/how-to-create-associations-between-types-class-designer.md). Pokud váš projekt obsahuje více diagramů tříd, změny, které provedete tak, jak diagramu zobrazí vztahy přidružení ovlivňují pouze tento diagram. Chcete-li změnit způsob, jakým jiného diagramu zobrazí vztahy přidružení, otevřete nebo zobrazit tento diagram a proveďte tyto kroky.  
  
### <a name="to-change-member-notation-to-association-notation"></a>Chcete-li změnit zápisem člena zápisem asociace  
  
1. Z uzlu projektu v Průzkumníku řešení otevřete soubor diagramu tříd (.cd).  
  
2. V obrazci typu v diagramu tříd, klikněte pravým tlačítkem na člen vlastnost nebo pole představující přidružení a zvolte **zobrazit jako přidružení**.  
  
    > [!TIP]
    > Pokud jsou viditelné ve tvaru typu žádné vlastnosti nebo pole, jsou sbaleny oddílů ve tvaru. Pokud chcete rozšířit tvar typu, dvakrát klikněte na název oddílu nebo pravým tlačítkem myši na tvar typu a zvolte **Rozbalit**.  
  
     Člen zmizí z prostoru ve tvaru typu a Asociační čára, zobrazí se dva typy připojení. Asociační čára označen názvem vlastnosti nebo pole.  
  
### <a name="to-change-association-notation-to-member-notation"></a>Chcete-li změnit zápisem asociace zápisem člena  
  
- V diagramu tříd, pravým tlačítkem myši na Asociační čára a zvolte **zobrazit jako vlastnost** nebo **zobrazit jako pole** podle potřeby.  
  
     Asociační čára zmizí, a vlastnost se zobrazí v odpovídající oddíl v rámci jeho tvar typu v diagramu.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Vytvoření dědičnosti mezi typy (návrhář tříd)](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [Postupy: Zobrazení dědičnosti mezi typy (návrhář tříd)](../ide/how-to-view-inheritance-between-types-class-designer.md)   
 [Zobrazování typů a vztahů (návrhář tříd)](../ide/viewing-types-and-relationships-class-designer.md)   
 [Postupy: Vizualizace asociace kolekce (Návrhář tříd)](../ide/how-to-visualize-a-collection-association-class-designer.md)
