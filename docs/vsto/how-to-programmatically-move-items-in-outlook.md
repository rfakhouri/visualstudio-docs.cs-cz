---
title: 'Postupy: Přesouvání položek v aplikaci Outlook prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook folders [Office development in Visual Studio], moving items
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b4551a7e1228203977cf04dc205445f3fe7d250c
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870737"
---
# <a name="how-to-programmatically-move-items-in-outlook"></a>Postupy: Přesouvání položek v aplikaci Outlook prostřednictvím kódu programu
  V tomto příkladu se přesune nepřečtených e-mailové zprávy z **doručené pošty** do složky s názvem **Test**. Příkladu se přesune pouze zprávy, které obsahují slovo **testovací** v `Subject` pole.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_OL_MoveItems#1](../vsto/codesnippet/CSharp/Trin_OL_MoveItems/thisaddin.cs#1)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Složku pošty aplikace Outlook s názvem **Test**.  
  
-   E-mailovou zprávu, která dorazí slovo **testovací** v `Subject` pole.  
  
## <a name="see-also"></a>Viz také:  
 [Práce se složkami](../vsto/working-with-folders.md)   
 [Postupy: Programově načítání složek podle názvu](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [Postupy: Hledání v rámci konkrétní složky prostřednictvím kódu programu](../vsto/how-to-programmatically-search-within-a-specific-folder.md)   
 [Postupy: Programově provádění akcí po přijetí e-mailovou zprávu](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
