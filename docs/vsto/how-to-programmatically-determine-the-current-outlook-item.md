---
title: 'Postupy: programové určení aktuální položky aplikace Outlook | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], current
- e-mail [Office development in Visual Studio], current item
- SelectionChange event
- Outlook [Office development in Visual Studio], current item
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e18c9fabd3d568d7663be9fecd6724edbafdbdfd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-determine-the-current-outlook-item"></a>Postupy: Určení aktuální položky aplikace Outlook prostřednictvím kódu programu
  Tento příklad používá událost Explorer.SelectionChange zobrazit název v aktuální složce a některé informace o vybrané položce. Kód pak zobrazí vybrané položky.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-vb[Trin_OL_CurrentItem#1](../vsto/codesnippet/VisualBasic/Trin_OL_CurrentItem/thisaddin.vb#1)]
 [!code-csharp[Trin_OL_CurrentItem#1](../vsto/codesnippet/CSharp/Trin_OL_CurrentItem/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Událost, obraťte se na a položek e-mailu v aplikaci Microsoft Office Outlook.  
  
## <a name="see-also"></a>Viz také  
 [Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md)   
 [Postupy: načítání složek podle názvu prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [Postupy: Hledání konkrétního kontaktu prostřednictvím kódu programu](../vsto/how-to-programmatically-search-for-a-specific-contact.md)  
  
  