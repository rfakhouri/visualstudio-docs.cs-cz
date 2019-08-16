---
title: 'Postupy: Programové odeslání e-mailu'
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], sending e-mail
- Outlook [Office development in Visual Studio], creating e-mail
- Outlook [Office development in Visual Studio], sending e-mail
- e-mail [Office development in Visual Studio], sending
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 72d033add2ba8320b14eebd5af700ab225d34410
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551751"
---
# <a name="how-to-programmatically-send-email"></a>Postupy: Programové odeslání e-mailu
  Tento příklad pošle e-mailovou zprávu kontaktům, které mají název domény **example.com** ve svých e-mailových adresách.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="example"></a>Příklad
 [!code-csharp[Trin_OL_ProgramEmail#1](../vsto/codesnippet/CSharp/Trin_OL_ProgramEMail/thisaddin.cs#1)]

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje:

- Kontakty, které mají název domény **example.com** ve svých e-mailových adresách.

## <a name="robust-programming"></a>Robustní programování
 Neodstraňujte kód filtru, který vyhledává název domény **example.com**. Pokud filtr odeberete, vaše řešení pošle e-mailové zprávy všem vašim kontaktům.

## <a name="see-also"></a>Viz také:
- [Práce s položkami pošty](../vsto/working-with-mail-items.md)
- [Postupy: Programové vytvoření e-mailové položky](../vsto/how-to-programmatically-create-an-e-mail-item.md)
- [Postupy: Programový přístup ke kontaktům aplikace Outlook](../vsto/how-to-programmatically-access-outlook-contacts.md)
- [Postupy: Při přijetí e-mailové zprávy programově provádět akce](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)
