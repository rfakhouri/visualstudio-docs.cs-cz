---
title: 'Postupy: Zabránění zobrazení oblasti formuláře Outlooku'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], canceling display
- canceling form region display
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: a7df2aef4348e95a30c0b14b26686764890b6abf
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53849740"
---
# <a name="how-to-prevent-outlook-from-displaying-a-form-region"></a>Postupy: Zabránění zobrazení oblasti formuláře Outlooku
  Můžou nastat situace, ve kterých nechcete, aby aplikace Microsoft Office Outlook k zobrazení oblasti formuláře pro určité položky. Například kontaktní položka neobsahuje adresu do zaměstnání, můžete zabránit oblasti formuláře, který zobrazuje umístění společnosti v objektu map povolí.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="to-prevent-outlook-from-displaying-a-form-region"></a>Pro zabránění zobrazení oblasti formuláře Outlooku  
  
1. Otevřete soubor kódu pro oblasti formuláře, který chcete upravit.  
  
2. Rozbalte **objekt pro vytváření oblasti formuláře** oblasti kódu.  
  
3. Přidejte kód, který `FormRegionInitializing` obslužná rutina události, která nastaví <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> vlastnost <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> třídu **true**.  
  
   V tomto příkladu, pokud položka kontaktu neobsahuje adresu <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> je nastavena na **true**, a oblasti formuláře se nezobrazí.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
 [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]  
  
## <a name="see-also"></a>Viz také:  
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Návod: Návrh oblasti formuláře Outlooku](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Postupy: Přidání oblasti formuláře do projektu doplňku aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Návod: Návrh oblasti formuláře Outlooku](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Návod: Import oblasti formuláře navržené v aplikaci Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
