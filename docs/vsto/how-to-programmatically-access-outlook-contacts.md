---
title: "Postupy: přístup programu ke kontaktům aplikace Outlook | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- contacts [Office development in Visual Studio], searching
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 4d4d88416507f7e63cd112df350dc93b2e13605f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
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
  
  