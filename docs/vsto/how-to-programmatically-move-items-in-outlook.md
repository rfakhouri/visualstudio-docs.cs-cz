---
title: "Postupy: přesouvání položek v aplikaci Outlook prostřednictvím kódu programu | Microsoft Docs"
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
helpviewer_keywords: Outlook folders [Office development in Visual Studio], moving items
ms.assetid: ac524f2e-a3e8-496d-bd5a-714799be44ab
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fc7afe28e435e0dcdd58c7403f6282ebf3609a23
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-move-items-in-outlook"></a>Postupy: Přesouvání položek v aplikaci Outlook prostřednictvím kódu programu
  Tento příklad přesune nepřečtené e-mailové zprávy z **doručené pošty** do složky s názvem **Test**. V příkladu přesouvá pouze zprávy, které mají slovo **Test** v `Subject` pole.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_OL_MoveItems#1](../vsto/codesnippet/CSharp/Trin_OL_MoveItems/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Složky aplikace Outlook e-mailu s názvem **Test**.  
  
-   E-mailové zprávy, které dorazí slovem **Test** v `Subject` pole.  
  
## <a name="see-also"></a>Viz také  
 [Práce se složkami](../vsto/working-with-folders.md)   
 [Postupy: načítání složek podle názvu prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [Postupy: hledání v rámci konkrétní složky prostřednictvím kódu programu](../vsto/how-to-programmatically-search-within-a-specific-folder.md)   
 [Postupy: prostřednictvím kódu programu provádění akcí po přijetí e-mailové zprávy](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
  
  