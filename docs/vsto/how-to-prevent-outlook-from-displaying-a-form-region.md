---
title: 'Postupy: zabránění zobrazení oblasti formuláře aplikace Outlook'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], canceling display
- canceling form region display
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 87a03e62c77730c7be2c9487c5e344d668ea62cc
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254785"
---
# <a name="how-to-prevent-outlook-from-displaying-a-form-region"></a>Postupy: zabránění zobrazení oblasti formuláře aplikace Outlook
  Můžou nastat situace, ve kterých nechcete, aby aplikace Microsoft Office Outlook k zobrazení oblasti formuláře pro konkrétní položku. Pokud položku kontaktní neobsahuje adresu firmy, abyste zabránili oblasti formuláře, který ukazuje umístění firmy v mapě ze storu.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="to-prevent-outlook-from-displaying-a-form-region"></a>Abyste zabránili zobrazení oblasti formuláře aplikace Outlook  
  
1.  Otevřete soubor kódu pro oblasti formuláře, který chcete upravit.  
  
2.  Rozbalte **Factory oblasti formuláře** kód oblasti.  
  
3.  Přidejte kód, který `FormRegionInitializing` obslužné rutiny události, která nastavuje <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> vlastnost <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> třídy k **true**.  
  
 V tomto příkladu, pokud položky kontaktu neobsahuje adresu <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> je nastavena na **true**, a oblasti formuláře se nezobrazí.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
 [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]  
  
## <a name="see-also"></a>Viz také:  
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Návod: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Postupy: přidání oblasti formuláře do projektu doplněk aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Návod: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Návod: Importujte oblasti formuláře navržené v aplikaci Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  