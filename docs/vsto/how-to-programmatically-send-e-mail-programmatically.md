---
title: 'Postupy: Odeslání e-mailu prostřednictvím kódu programu'
ms.date: 02/02/2017
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
ms.openlocfilehash: 51546047a12e23c688ccfdfd05aeaa9c2ab89f95
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54866724"
---
# <a name="how-to-programmatically-send-email"></a>Postupy: Odeslání e-mailu prostřednictvím kódu programu  
  Tento příklad odešle e-mailovou zprávu na kontakty, které mají název domény **example.com** jejich e-mailové adresy.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_OL_ProgramEmail#1](../vsto/codesnippet/CSharp/Trin_OL_ProgramEMail/thisaddin.cs#1)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Kontakty, které mají název domény **example.com** jejich e-mailové adresy.  
  
## <a name="robust-programming"></a>Robustní programování  
 Neodebírejte filtr kód, který hledá název domény **example.com**. Vaše řešení pošle e-mailové zprávy na všechny kontakty Pokud filtr odeberete.  
  
## <a name="see-also"></a>Viz také:  
 [Práce s položkami pošty](../vsto/working-with-mail-items.md)   
 [Postupy: Programové vytváření položek e-mailu](../vsto/how-to-programmatically-create-an-e-mail-item.md)   
 [Postupy: Programový přístup ke kontaktům aplikace Outlook](../vsto/how-to-programmatically-access-outlook-contacts.md)   
 [Postupy: Programově provádění akcí po přijetí e-mailovou zprávu](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
