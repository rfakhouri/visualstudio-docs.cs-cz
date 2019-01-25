---
title: 'Postupy: Přidávání obrazců do dokumentů aplikace Visio prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], adding Visio shapes
- shapes [Office development in Visual Studio], adding Visio shapes
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: accb45527d73c041600dd3216c85e54bdadd5f4a
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54862600"
---
# <a name="how-to-programmatically-add-shapes-to-a-visio-document"></a>Postupy: Přidávání obrazců do dokumentů aplikace Visio prostřednictvím kódu programu
  Tvary můžete přidat do dokumentu aplikace Microsoft Office Visio načítání si hlavní počítače z vzorníku a umístěním tvary na aktivní stránce.  
  
 Další informace najdete v tématu referenční dokumentaci jazyka VBA pro [Microsoft.Office.Interop.Visio.Documents.Add](/office/vba/api/Visio.Documents.Add) metody [Microsoft.Office.Interop.Visio.Application.ActivePage](/office/vba/api/Visio.Application.ActivePage) vlastnosti a [Microsoft.Office.Interop.Visio.Page.Drop](/office/vba/api/Visio.Page.Drop) metody.  
  
## <a name="add-shapes-to-a-visio-document"></a>Přidávání obrazců do dokumentů aplikace Visio  
  
### <a name="to-add-shapes-to-a-visio-document"></a>K přidávání obrazců do dokumentů aplikace Visio  
  
-   S aktivním dokumentem načtěte si hlavní počítače z kolekce Documents.Masters a vyřadit tvary v aktivním dokumentu. Hlavní můžete načíst pomocí index nebo název předlohy.  
  
     Následující příklad kódu vytvoří prázdný dokument Visia a pak ho otevře **základních tvarů** vzorníku ukotven. Kód poté načte několik tvarů a sníží na aktivní stránce.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>Viz také:  
 [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Práce s obrazci aplikace Visio](../vsto/working-with-visio-shapes.md)   
 [Postupy: Programově kopírování a vkládání obrazců do dokumentů aplikace Visio](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)  
