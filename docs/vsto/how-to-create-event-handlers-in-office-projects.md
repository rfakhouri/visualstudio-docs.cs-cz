---
title: 'Postupy: Vytváření obslužných rutin událostí v projektech pro systém Office'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Basic [Office development in Visual Studio], event handlers
- event handlers [Office development in Visual Studio]
- Visual C# [Office development in Visual Studio], event handlers
- events [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f2a7661a1bce8e1ff6152040fe5b8d5567b55c7e
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54863835"
---
# <a name="how-to-create-event-handlers-in-office-projects"></a>Postupy: Vytváření obslužných rutin událostí v projektech pro systém Office
  Existuje několik způsobů, jak vytváření obslužných rutin událostí v jazyce Visual Basic a C#. V návrhovém zobrazení můžete vytvořit výchozí obslužné rutiny událostí pro ovládací prvky poklepáním na ovládací prvek, nebo použijte v podokně události **vlastnosti** okno pro vytvoření obslužné rutiny pro všechny události v ovládacím prvku. Pokud jste v zobrazení kódu, nemusí však chcete přepnout do zobrazení návrhu k vytvoření obslužné rutiny události.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-create-an-event-handler-in-visual-basic"></a>Chcete-li vytvořit obslužnou rutinu události v jazyce Visual Basic  
  
1.  Z **název třídy** rozevíracího seznamu v horní části stránky Editor kódu, vyberte objekt, který chcete vytvořit obslužná rutina události.  
  
    > [!NOTE]  
    >  Pokud chcete vytvořit obslužné rutiny událostí pro `ThisDocument` nebo `ThisWorkbook`, je nutné vybrat **(ThisDocument události)** nebo **(ThisWorkbook události)** v **název třídy**rozevíracího seznamu  
  
2.  Z **název metody** rozevíracího seznamu v horní části stránky Editor kódu, zvolit událost.  
  
     Visual Studio vytvoří obslužnou rutinu události a přesune kurzor obslužné rutiny události na nově vytvořený. Pokud již existuje obslužná rutina události, kurzor se přesune do existující obslužné rutiny události.  
  
### <a name="to-create-an-event-handler-in-c"></a>Chcete-li vytvořit obslužnou rutinu události vC#  
  
1.  Vytvoření delegáta události v **spuštění** událost třídy zadáte název kvalifikovaný události, za nímž následuje mezera a zadáním **+=** později bez mezer. Příklad:  
  
     `this.<object name>.<event name> +=`  
  
2.  Na konci řádku kódu stiskněte klávesu Tabulátor dvakrát.  
  
     Visual Studio automaticky dokončí řádek kódu vytvoří obslužnou rutinu události a přesune kurzor obslužné rutiny události na nově vytvořený.  
  
## <a name="see-also"></a>Viz také:  
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Návod: Program ošetření událostí ovládacího prvku NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Vytváření řešení pro systém Office](../vsto/building-office-solutions.md)  
