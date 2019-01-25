---
title: 'Postupy: Určení aktuální položky aplikace Outlook prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], current
- e-mail [Office development in Visual Studio], current item
- SelectionChange event
- Outlook [Office development in Visual Studio], current item
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e72928c6244ba15a96bdedd7aba6b59c1e50e708
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54875092"
---
# <a name="how-to-programmatically-determine-the-current-outlook-item"></a>Postupy: Určení aktuální položky aplikace Outlook prostřednictvím kódu programu
  V tomto příkladu `Explorer.SelectionChange` události zobrazovaný název aktuální složky a některé informace o vybrané položce. Kód poté zobrazí vybranou položku.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-vb[Trin_OL_CurrentItem#1](../vsto/codesnippet/VisualBasic/Trin_OL_CurrentItem/thisaddin.vb#1)]
 [!code-csharp[Trin_OL_CurrentItem#1](../vsto/codesnippet/CSharp/Trin_OL_CurrentItem/thisaddin.cs#1)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Událost, kontaktů a položek e-mailu v Microsoft Office Outlook.  
  
## <a name="see-also"></a>Viz také:  
 [Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md)   
 [Postupy: Programově načítání složek podle názvu](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [Postupy: Hledání konkrétního kontaktu prostřednictvím kódu programu](../vsto/how-to-programmatically-search-for-a-specific-contact.md)  
