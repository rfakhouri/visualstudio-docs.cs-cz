---
title: 'Postupy: Načítání nepřečtených zpráv ze složky Doručená pošta prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- e-mail [Office development in Visual Studio], unread mail
- Outlook [Office development in Visual Studio], unread mail
- unread e-mail
- mail items [Office development in Visual Studio], unread mail
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b618d09fb8b11f98077ab3bb49e32a28869e5b04
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955651"
---
# <a name="how-to-programmatically-retrieve-unread-messages-from-the-inbox"></a>Postupy: Načítání nepřečtených zpráv ze složky Doručená pošta prostřednictvím kódu programu
  Tento příklad načte nepřečtených e-mailové zprávy z aplikace Outlook **doručené pošty** a zobrazuje počet položek.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Příklad
 [!code-vb[Trin_Outlook_RL_UnreadItems#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_RL_UnreadItems/thisaddin.vb#1)]
 [!code-csharp[Trin_Outlook_RL_UnreadItems#1](../vsto/codesnippet/CSharp/Trin_Outlook_RL_UnreadItems/thisaddin.cs#1)]

## <a name="see-also"></a>Viz také:
- [Práce s položkami pošty](../vsto/working-with-mail-items.md)
- [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)
- [Postupy: Programové vytváření položek e-mailu](../vsto/how-to-programmatically-create-an-e-mail-item.md)
- [Postupy: Odeslání e-mailu prostřednictvím kódu programu](../vsto/how-to-programmatically-send-e-mail-programmatically.md)
- [Postupy: Programově provádění akcí po přijetí e-mailovou zprávu](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)
