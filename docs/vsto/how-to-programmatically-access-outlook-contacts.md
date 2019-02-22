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
ms.openlocfilehash: c46df4218a12c0f9a155567aeee0c007d0a19c53
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56598203"
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

-   Kontakty, jehož poslední názvy obsahují řetězec "**Na"** (například Tzipi Butnaru) v **kontakty** složky.

## <a name="see-also"></a>Viz také:
- [Práce s položkami kontaktů](../vsto/working-with-contact-items.md)
- [Postupy: Přidávání položky ke kontaktům aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md)
- [Postupy: Hledání konkrétního kontaktu prostřednictvím kódu programu](../vsto/how-to-programmatically-search-for-a-specific-contact.md)
- [Postupy: Hledání e-mailových adres v kontaktech prostřednictvím kódu programu](../vsto/how-to-programmatically-search-for-an-e-mail-address-in-contacts.md)
- [Postupy: Odstraňování kontaktů aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-delete-outlook-contacts.md)
