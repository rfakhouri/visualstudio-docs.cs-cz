---
title: "Postupy: vytváření obslužných rutin událostí v projektech Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Basic [Office development in Visual Studio], event handlers
- event handlers [Office development in Visual Studio]
- Visual C# [Office development in Visual Studio], event handlers
- events [Office development in Visual Studio]
ms.assetid: 2cfd6a45-4c25-4431-b4fc-e0f2c0a72e54
caps.latest.revision: "31"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: af681832a8c298427c13060d858b57b99654953a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-event-handlers-in-office-projects"></a>Postupy: Vytváření obslužných rutin událostí v projektech pro systém Office
  Existuje několik způsobů vytvoření obslužné rutiny událostí v jazyce Visual Basic a C#. V návrhovém zobrazení můžete vytvořit výchozí obslužné rutiny události pro ovládací prvky poklepáním na ovládací prvek nebo pomocí podokna události **vlastnosti** okno pro vytvoření obslužné rutiny pro všechny události v ovládacím prvku. Pokud jste v zobrazení kódu, nemusí ale chcete přepnout do zobrazení návrhu a vytvořit obslužnou rutinu události.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-create-an-event-handler-in-visual-basic"></a>Pro vytvoření obslužné rutiny událostí v jazyce Visual Basic  
  
1.  Z **název třídy** rozevírací seznam v horní části editoru kódu, vyberte objekt, který chcete vytvořit obslužnou rutinu události pro.  
  
    > [!NOTE]  
    >  Pokud chcete vytvořit obslužné rutiny pro `ThisDocument` nebo `ThisWorkbook`, je nutné vybrat **(ThisDocument událostí)** nebo **(ThisWorkbook událostí)** v **název třídy**rozevíracího seznamu  
  
2.  Z **název metody** rozevírací seznam v horní části editoru kódu, vyberte události.  
  
     Visual Studio vytvoří obslužné rutiny události a Posune kurzor na nově vytvořený obslužné rutině. Pokud obslužná rutina události již existuje, kurzor se přesune do stávající obslužné rutiny události.  
  
### <a name="to-create-an-event-handler-in-c"></a>Pro vytvoření obslužné rutiny událostí v jazyce C#  
  
1.  Vytvoření delegát události v **spuštění** událostí třídy zadáním názvu kvalifikovaný události následované mezerou a zadáním  **+=**  bez mezery později. Příklad:  
  
     `this.<object name>.<event name> +=`  
  
2.  Na konci řádku kódu stiskněte klávesu Tabulátor dvakrát.  
  
     Visual Studio automaticky dokončení řádek kódu, vytvoří obslužné rutiny události a Posune kurzor na nově vytvořený obslužné rutině.  
  
## <a name="see-also"></a>Viz také  
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Návod: Programové ošetření událostí ovládacího prvku NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Vytváření řešení pro systém Office](../vsto/building-office-solutions.md)  
  
  