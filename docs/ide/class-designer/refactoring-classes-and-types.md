---
title: "Refaktoring tříd a typů (návrhář tříd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.ClassDesigner.OverrideMembersDialog
helpviewer_keywords:
- members, overriding
- overriding members
- classes [Visual Studio], refactoring
- type members, overriding
- refactoring, types
- types [Visual Studio], refactoring
- Class Designer [Visual Studio], refactoring classes
- refactoring, classes
ms.assetid: dcf07bb4-fa3b-4224-9dec-566fd924a8ce
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2724e10d88662ddd60167599139fa401d0c57387
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/15/2017
---
# <a name="refactoring-classes-and-types-class-designer"></a>Refaktoring tříd a typů (návrhář tříd)
Při zrefaktorujete kódu, které usnadňují pochopit, údržbu a efektivnější změnou jeho interní struktuře a způsobu jeho objektů navržený, ne jeho externí chování. Návrhář tříd a okně podrobností třídy použijte ke snížení práci, kterou je nutné provést a riziko představení chyb při Refaktorovat kódu Visual C# .NET, Visual Basic .NET nebo C++ v projektu sady Visual Studio.  
  
> [!NOTE]
>  Soubory projektu může být jen pro čtení, protože projekt je ve správě zdrojového kódu a není rezervována; je odkazovaná projektu. nebo jeho soubory jsou označeny jako jen pro čtení na disku. Pokud pracujete v projektu v některém z těchto stavů, zobrazí se různé způsoby, jak uložit práci v závislosti na stavu projektu. To platí refaktoringu kód a kód, který změníte jiným způsobem, např. úpravy ji přímo. Další informace najdete v tématu [zobrazení jen pro čtení informací](http://msdn.microsoft.com/en-us/33e2d3a9-1668-4d10-ae56-fa09b3156e0a).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Podpůrný obsah|  
|----------|------------------------|  
|**Refaktoring tříd:** refaktoringu operace můžete použít k rozdělení třídy na částečné třídy nebo k implementaci abstraktní základní třídu.|-   [Postupy: rozdělení třídy na částečné třídy](how-to-split-a-class-into-partial-classes.md)|  
|**Práce s rozhraní:** v Návrháři tříd můžete implementovat rozhraní v diagramu tříd propojením na třídu, která obsahuje kód pro metodu rozhraní.|-   [Postupy: implementace rozhraní](how-to-implement-an-interface.md)|  
|**Refaktoring typy, členy typu a parametry:** pomocí návrháře tříd můžete přejmenovat typy, přepsat členy typu nebo přesunuty z jednoho typu do jiného. Můžete také vytvořit typy s možnou hodnotou Null.|-   [Přejmenování typy a členy typu](refactoring-classes-and-types.md#RenamingTypesAndMembers)<br />-   [Přesunutí členy typu ze jeden typ](refactoring-classes-and-types.md#MovingTypeMembers)<br />-   [Postupy: vytvoření typu s povolenou hodnotou Null](how-to-create-a-nullable-type.md)|  
  
###  <a name="RenamingTypesAndMembers"></a>Přejmenování typy a členy typu  
V Návrháři tříd můžete přejmenovat typ nebo člen typu v diagramu tříd nebo v okně Vlastnosti. V okně podrobností třídy můžete změnit název člena, ale není typu. Přejmenování typ nebo člen typu rozšíří na všechny windows a kód umístění, kde se objevil starý název.  
  
##### <a name="to-rename-a-name-in-the-class-designer"></a>Chcete-li přejmenovat název v Návrháři tříd  
  
1.  Na diagramu tříd vyberte typ nebo člen a klikněte na název.  
  
     Název člena možné upravovat.  
  
2.  Zadejte nový název pro typ nebo člen typu  
  
##### <a name="to-rename-a-name-in-the-class-details-window"></a>Chcete-li přejmenovat název v okně podrobností třídy  
  
1.  Pokud chcete zobrazit okno podrobností třídy, klikněte pravým tlačítkem na typ nebo člen typu a potom klikněte na **podrobností třídy**.  
  
     Zobrazí se okno podrobností třídy.  
  
2.  V **název** sloupce, změňte název člena typu  
  
3.  Chcete-li přesunout fokus od buňky, stiskněte **ENTER** klíče nebo klikněte na tlačítko od buňky.  
  
    > [!NOTE]
    >  V okně podrobností třídy můžete změnit název člena, ale není typu.  
  
##### <a name="to-rename-a-name-in-the-properties-window"></a>Chcete-li přejmenovat název v okně vlastností  
  
1.  V diagramu tříd nebo v okně podrobností třídy, klikněte pravým tlačítkem na typ nebo člen a pak klikněte na **vlastnosti**.  
  
     Okno vlastností se zobrazí a zobrazí vlastnosti pro typ nebo člen typu.  
  
2.  V **název** vlastnost, změňte název typu nebo typ člena.  
  
     Nový název rozšíří na všechny windows a kód umístění v aktuálním projektu, kde se objevil starý název.  
  
###  <a name="MovingTypeMembers"></a>Přesunutí členy typu ze jeden typ  
Pomocí **návrhář tříd**, můžete přesunout člena typu jeden typ na jiný typ, pokud jsou obě viditelné v aktuální diagramu tříd.  
  
##### <a name="to-move-a-type-member-from-one-type-to-another"></a>K přesunutí člena typu ze jeden typ  
  
1.  V typu, který je viditelný na návrhovou plochu, klikněte pravým tlačítkem na člena, který chcete přesunout na jiný typ a pak klikněte na tlačítko **Vyjmout**.  
  
2.  Klikněte pravým tlačítkem na typ cílového a pak klikněte na **vložení**.  
  
     Vlastnost se odebere z typ zdroje a zobrazí se v cílovém typu.  
  
## <a name="see-also"></a>Viz také
[Zobrazování typů a vztahů](viewing-types-and-relationships.md)  
[Navrhování tříd a typů](designing-classes-and-types.md)