---
title: 'Postupy: odesílání e-mailu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
manager: douge
ms.workload:
- office
ms.openlocfilehash: c3ee656a8a4965f01969bad19d66d0ea6215bcbe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
  
  