---
title: Ukládání příloh položek e-mailu aplikace Outlook prostřednictvím kódu programu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- CSharp
helpviewer_keywords:
- Outlook [Office development in Visual Studio], attachments
- e-mail [Office development in Visual Studio], attachments
- saving e-mail attachments
- mail items [Office development in Visual Studio], attachments
- attachments [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e7e0cff4761b26bac8265592b681d4e56f2ad92f
ms.sourcegitcommit: 7eb2fb21805d92f085126f3a820ac274f2216b4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2019
ms.locfileid: "67328954"
---
# <a name="how-to-programmatically-save-attachments-from-outlook-email-items"></a>Postupy: Ukládání příloh položek e-mailu aplikace Outlook prostřednictvím kódu programu

V tomto příkladu se uloží přílohy e-mailů do zadané složky při přijetí e-mailu v doručené poště.

> [!IMPORTANT]
> Tento příklad funguje pouze v případě, že přidáte složku s názvem **TestFileSave** v kořenovém adresáři.

[!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Příklad

[!code-csharp[Trin_OL_SaveAttachments#1](../vsto/codesnippet/CSharp/Trin_OL_SaveAttachments/thisaddin.cs#1)]

## <a name="see-also"></a>Viz také:

- [Práce s položkami pošty](../vsto/working-with-mail-items.md)
- [Postupy: Programově načítání složek podle názvu](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)
- [Postupy: Programově provádění akcí po přijetí e-mailovou zprávu](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)
- [Postupy: Hledání v rámci konkrétní složky prostřednictvím kódu programu](../vsto/how-to-programmatically-search-within-a-specific-folder.md)
