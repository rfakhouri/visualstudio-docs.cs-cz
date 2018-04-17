---
title: 'Postupy: hledání e-mailových adres v kontaktech prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- e-mail [Office development in Visual Studio], searching
- contacts [Office development in Visual Studio], searching
- searching contacts
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 16b79f5f14f1e0d8c5c82a00f5f2ccf2412b991b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-search-for-an-e-mail-address-in-contacts"></a>Postupy: Hledání e-mailových adres v kontaktech prostřednictvím kódu programu
  Tento příklad vyhledá kontaktní složku pro kontakty, které mají název domény **example.com** v e-mailových adres.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_OL_SearchEmail#1](../vsto/codesnippet/CSharp/Trin_OL_SearchEmail/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Kontakty, které mají název domény **example.com** v e-mailových adres (například `somebody@example.com`), a které mají názvy první a poslední.  
  
## <a name="see-also"></a>Viz také  
 [Práce s položkami kontaktů](../vsto/working-with-contact-items.md)   
 [Postupy: odeslání e-mailu prostřednictvím kódu programu](../vsto/how-to-programmatically-send-e-mail-programmatically.md)   
 [Postupy: přístup programu ke kontaktům aplikace Outlook](../vsto/how-to-programmatically-access-outlook-contacts.md)   
 [Postupy: Přidání položky ke kontaktům aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md)  
  
  