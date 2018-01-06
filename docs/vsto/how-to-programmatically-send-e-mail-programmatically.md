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
ms.assetid: 4fa0e1b5-2caf-4a11-8626-df643b23f5f0
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 39a0ebee37c57630649f680d14aa8fef22833225
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
  