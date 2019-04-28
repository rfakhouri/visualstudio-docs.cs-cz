---
title: 'Postupy: Programový přístup ke kontaktům aplikace Outlook'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- contacts [Office development in Visual Studio], searching
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a9fc9cf214a8aebd663a7de29528790aa3cc0b46
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967680"
---
# <a name="how-to-programmatically-access-outlook-contacts"></a>Postupy: Programový přístup ke kontaktům aplikace Outlook
  Tento příklad vyhledá všechny kontakty, jejichž příjmení obsahuje zadaný hledaný řetězec.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Příklad
 [!code-csharp[Trin_OL_AccessContacts#1](../vsto/codesnippet/CSharp/Trin_OL_AccessContacts.trin_ol_accesscontacts/thisaddin.cs#1)]
 [!code-csharp[Trin_OL_AccessContacts#1](../vsto/codesnippet/CSharp/Trin_OL_AccessContacts.trin_ol_accesscontacts/thisaddin.cs#1)]
 [!code-vb[Trin_OL_AccessContacts#1](../vsto/codesnippet/VisualBasic/Trin_OL_AccessContacts/thisaddin.vb#1)]

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje:

- Kontakty, jehož poslední názvy obsahují řetězec "**Na"** (například Tzipi Butnaru) v **kontakty** složky.

## <a name="see-also"></a>Viz také:
- [Práce s položkami kontaktů](../vsto/working-with-contact-items.md)
- [Postupy: Přidávání položky ke kontaktům aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md)
- [Postupy: Hledání konkrétního kontaktu prostřednictvím kódu programu](../vsto/how-to-programmatically-search-for-a-specific-contact.md)
- [Postupy: Hledání e-mailových adres v kontaktech prostřednictvím kódu programu](../vsto/how-to-programmatically-search-for-an-e-mail-address-in-contacts.md)
- [Postupy: Odstraňování kontaktů aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-delete-outlook-contacts.md)
