---
title: 'Postupy: Připojování souborů k položkám e-mailu aplikace Outlook prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook [Office development in Visual Studio], attachments
- e-mail [Office development in Visual Studio], attachments
- mail items [Office development in Visual Studio], attachments
- attachments [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 707c3bb2b6bec9f8db1744d1f28acd4e90a45a57
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62575621"
---
# <a name="how-to-programmatically-attach-files-to-outlook-email-items"></a>Postupy: Připojování souborů k položkám e-mailu aplikace Outlook prostřednictvím kódu programu
  Tento příklad připojí do souboru s položkou nové e-mailu a odesílá je do Armando Pinto. Příklad předpokládá, že osoba s názvem Armando Pinto existuje jako příjemce.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Příklad
 [!code-csharp[Trin_Outlook_RL_AttachFiles#1](../vsto/codesnippet/CSharp/Trin_Outlook_RL_AttachFiles/thisaddin.cs#1)]
 [!code-vb[Trin_Outlook_RL_AttachFiles#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_RL_AttachFiles/thisaddin.vb#1)]

## <a name="see-also"></a>Viz také:
- [Práce s položkami pošty](../vsto/working-with-mail-items.md)
- [Postupy: Odeslání e-mailu prostřednictvím kódu programu](../vsto/how-to-programmatically-send-e-mail-programmatically.md)
- [Postupy: Ukládání příloh položek e-mailu aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-save-attachments-from-outlook-e-mail-items.md)
- [Postupy: Programové vytváření položek e-mailu](../vsto/how-to-programmatically-create-an-e-mail-item.md)
