---
title: Pokud dostali e-mailové zprávy prostřednictvím kódu programu provádět akce
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook [Office development in Visual Studio], actions when e-mail is received
- NewMail event
- mail items [Office development in Visual Studio], custom actions
- e-mail [Office development in Visual Studio], custom actions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a0787db2f7055bc65871227b9fcf8cbbb60ec1d8
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402202"
---
# <a name="how-to-programmatically-perform-actions-when-an-email-message-is-received"></a>Postupy: Programově provádění akcí po přijetí e-mailovou zprávu
  V tomto příkladu provede vlastní akce, když je uživateli doručeno e-mailovou zprávu.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Příklad
 [!code-vb[Trin_Outlook_RL_PerformActions#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_RL_PerformActions/thisaddin.vb#1)]
 [!code-csharp[Trin_Outlook_RL_PerformActions#1](../vsto/codesnippet/CSharp/Trin_Outlook_RL_PerformActions/thisaddin.cs#1)]

## <a name="see-also"></a>Viz také:
- [Postupy: Vytváření obslužných rutin událostí v projektech pro systém Office](../vsto/how-to-create-event-handlers-in-office-projects.md)
- [Práce s položkami pošty](../vsto/working-with-mail-items.md)
- [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)
