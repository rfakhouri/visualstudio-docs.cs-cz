---
title: "Postupy: ukládání příloh z položek e-mailu aplikace Outlook prostřednictvím kódu programu | Microsoft Docs"
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
- Outlook [Office development in Visual Studio], attachments
- e-mail [Office development in Visual Studio], attachments
- saving e-mail attachments
- mail items [Office development in Visual Studio], attachments
- attachments [Office development in Visual Studio]
ms.assetid: 2f05e2bb-ae4f-407c-a6da-a3b1a4c31ab3
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 50673163fdbdd1c0927f6efa56eae39e8cc2e3c8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-save-attachments-from-outlook-e-mail-items"></a>Postupy: Ukládání příloh položek e-mailu aplikace Outlook prostřednictvím kódu programu
  Tento příklad uloží přílohy e-mailů do zadané složky při obdržení e-mailu v doručené poště.  
  
> [!IMPORTANT]  
>  Tento příklad funguje pouze v případě, že přidáte do složky s názvem **TestFileSave** v kořenovém adresáři C.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_OL_SaveAttachments#1](../vsto/codesnippet/CSharp/Trin_OL_SaveAttachments/thisaddin.cs#1)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s položkami pošty](../vsto/working-with-mail-items.md)   
 [Postupy: načítání složek podle názvu prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [Postupy: prostřednictvím kódu programu provádění akcí po přijetí e-mailové zprávy](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)   
 [Postupy: hledání v rámci konkrétní složky prostřednictvím kódu programu](../vsto/how-to-programmatically-search-within-a-specific-folder.md)  
  
  