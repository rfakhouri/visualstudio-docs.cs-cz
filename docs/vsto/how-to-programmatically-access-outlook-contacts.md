---
title: 'Postupy: přístup programu ke kontaktům aplikace Outlook | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- contacts [Office development in Visual Studio], searching
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c48a58a4215ce73bcc6e9f4593819cbbdbed1693
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-access-outlook-contacts"></a>Postupy: Přístup ke kontaktům aplikace Outlook prostřednictvím kódu programu
  Tento příklad vyhledá všechny kontakty, jejichž příjmení obsahuje zadaný hledaný řetězec.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_OL_AccessContacts#1](../vsto/codesnippet/CSharp/Trin_OL_AccessContacts.trin_ol_accesscontacts/thisaddin.cs#1)]
 [!code-csharp[Trin_OL_AccessContacts#1](../vsto/codesnippet/CSharp/Trin_OL_AccessContacts.trin_ol_accesscontacts/thisaddin.cs#1)]
 [!code-vb[Trin_OL_AccessContacts#1](../vsto/codesnippet/VisualBasic/Trin_OL_AccessContacts/thisaddin.vb#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Kontakty, jejichž příjmení obsahují řetězec "**Na"** (například Tzipi Butnaru) v **kontakty** složky.  
  
## <a name="see-also"></a>Viz také  
 [Práce s položkami kontaktů](../vsto/working-with-contact-items.md)   
 [Postupy: přidávání položku ke kontaktům aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md)   
 [Postupy: hledání konkrétního kontaktu prostřednictvím kódu programu](../vsto/how-to-programmatically-search-for-a-specific-contact.md)   
 [Postupy: hledání e-mailových adres v kontaktech prostřednictvím kódu programu](../vsto/how-to-programmatically-search-for-an-e-mail-address-in-contacts.md)   
 [Postupy: Odstraňování kontaktů aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-delete-outlook-contacts.md)  
  
  