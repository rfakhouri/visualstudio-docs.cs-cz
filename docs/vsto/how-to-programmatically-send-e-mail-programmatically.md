---
title: "Postupy: odesílání e-mailu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], sending e-mail
- Outlook [Office development in Visual Studio], creating e-mail
- Outlook [Office development in Visual Studio], sending e-mail
- e-mail [Office development in Visual Studio], sending
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: f8681fecf8dc2d4c3a26aeaeb372faeb57e54094
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-send-e-mail"></a>Postupy: odeslání e-mailu prostřednictvím kódu programu  
  Tento příklad odešle e-mailová zpráva kontakty, které mají název domény **example.com** v e-mailových adres.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_OL_ProgramEmail#1](../vsto/codesnippet/CSharp/Trin_OL_ProgramEMail/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Kontakty, které mají název domény **example.com** v e-mailových adres.  
  
## <a name="robust-programming"></a>Robustní programování  
 Neodebírejte filtru kód, který hledá název domény **example.com**. Řešení se pošle e-mailové zprávy na všechny kontakty, pokud odeberete filtru.  
  
## <a name="see-also"></a>Viz také  
 [Práce s položkami pošty](../vsto/working-with-mail-items.md)   
 [Postupy: vytváření položek e-mailu prostřednictvím kódu programu](../vsto/how-to-programmatically-create-an-e-mail-item.md)   
 [Postupy: přístup programu ke kontaktům aplikace Outlook](../vsto/how-to-programmatically-access-outlook-contacts.md)   
 [Postupy: Provádění akcí po přijetí e-mailové zprávy prostřednictvím kódu programu](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
  
  