---
title: "Postupy: přidávání obrazců do dokumentů aplikace Visio prostřednictvím kódu programu | Microsoft Docs"
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
- Visio [Office development in Visual Studio], adding Visio shapes
- shapes [Office development in Visual Studio], adding Visio shapes
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4d73c59ac9ba89a5814a264bb8e8fe3c83b9789e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-add-shapes-to-a-visio-document"></a>Postupy: Přidávání obrazců do dokumentů aplikace Visio prostřednictvím kódu programu
  Tvary můžete přidat do dokumentu aplikace Microsoft Office Visio načítání je hlavní servery z vzorníku a umístěním obrazce na stránce active.  
  
 Další informace najdete v tématu referenční dokumentaci VBA pro [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) metody [Microsoft.Office.Interop.Visio.Application.ActivePage](http://msdn.microsoft.com/library/office/ff765484.aspx) vlastnost a [Microsoft.Office.Interop.Visio.Page.Drop](http://msdn.microsoft.com/library/office/ff765054.aspx) metoda.  
  
## <a name="adding-shapes-to-a-visio-document"></a>Přidávání obrazců do dokumentů aplikace Visio  
  
#### <a name="to-add-shapes-to-a-visio-document"></a>K přidávání obrazců do dokumentů aplikace Visio  
  
-   S aktivním dokumentem načíst je hlavní servery z kolekce Documents.Masters a odpojit obrazce v aktivním dokumentu. Hlavní server můžete načíst pomocí indexu nebo hlavní název.  
  
     Následující příklad kódu vytvoří prázdné dokumentů aplikace Visio a pak ho se otevře **základní tvary** vzorníku ukotven. Kód pak načte několik tvarů a zahodí je na stránce aktivní.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>Viz také  
 [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Práce s obrazci aplikace Visio](../vsto/working-with-visio-shapes.md)   
 [Postupy: Kopírování a vkládání obrazců do dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)  
  
  