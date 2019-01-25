---
title: 'Postupy: Přidání oblasti formuláře do projektu doplňku aplikace Outlook'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.Page1
- VSTO.NewFormRegionWizard.Page3
- VSTO.NewFormRegionWizard.Page2
- VSTO.NewFormRegionWizard.Page0
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], adding
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: adc1b788c01dca16663fa769ffd69904b04e8a98
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870997"
---
# <a name="how-to-add-a-form-region-to-an-outlook-add-in-project"></a>Postupy: Přidání oblasti formuláře do projektu doplňku aplikace Outlook
  Vytvoření oblasti formuláře rozšířit standardní nebo vlastní formulář aplikace Microsoft Office Outlook s použitím **novou oblast formuláře Outlooku** průvodce. Můžete vytvořit novou oblast formuláře a návrh uživatelského rozhraní v sadě Visual Studio, nebo můžete import oblasti formuláře, která je navržená v Outlooku a přidání Visual Basic nebo C# kódu.  
  
 Pokud máte oblasti formuláře Outlooku, který jste použili v jiném projektu aplikace Outlook, jej můžete znovu použít v aktuálním projektu doplňku VSTO pro Outlook s použitím **přidat existující položku** dialogové okno. Další informace najdete v tématu [oblastí formulářů aplikace Outlook vytvořit](../vsto/creating-outlook-form-regions.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
### <a name="to-add-a-new-form-region-to-an-outlook-project"></a>Chcete-li přidat novou oblast formuláře do projektu aplikace Outlook  
  
1.  Otevřete nebo vytvořte projekt doplňku VSTO pro Outlook v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Další informace najdete v tématu [jak: Vytvářet projekty pro Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  V **Průzkumníka řešení**, vyberte uzel projektu doplňku VSTO v Outlooku.  
  
3.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
4.  V **přidat novou položku** dialogu **oblast formuláře Outlooku**.  
  
5.  Zadejte název pro oblasti formuláře v **název** pole a potom klikněte na tlačítko **přidat**.  
  
     **Oblasti formuláře NewOutlook** spustí se průvodce.  
  
6.  Na **vyberte způsob vytvoření oblasti formuláře** vyberte, zda chcete návrh oblasti formuláře pomocí přetahování spravovaných ovládacích prvků na vizuálního návrháře nebo import oblasti formuláře, která je navržená v Outlooku.  
  
    > [!NOTE]  
    >  Pokud zvolíte import oblasti formuláře, která je navržená v Outlooku, pak je nutné zadat umístění úložiště formulářů Outlooku (*.ofs*) soubor. Spravované ovládací prvky nelze přidat do oblasti formuláře navržené v aplikaci Outlook; pouze můžete přidat kód za existující uživatelského rozhraní. Další informace najdete v tématu [oblastí formulářů aplikace Outlook vytvořit](../vsto/creating-outlook-form-regions.md).  
  
7.  Na **výběr typu oblasti formuláře chcete vytvořit** stránce zkontrolujte oblasti formuláře typu a vyberte jeden a pak klikněte na tlačítko **Další**. Další informace o oblasti formuláře typu naleznete v tématu [oblastí formulářů aplikace Outlook vytvořit](../vsto/creating-outlook-form-regions.md).  
  
8.  Na **zadání popisného textu a výběr předvoleb zobrazení** stránku, **název** zadejte název pro oblasti formuláře. Pro nahrazení a nahradit všechno formuláře oblasti typy **Title** a **popis** polí jsou také k dispozici.  
  
     Informace o tom, kde název, název a popis se zobrazí v aplikaci Outlook při nasazování oblasti formuláře, naleznete v tématu [oblastí formulářů aplikace Outlook vytvořit](../vsto/creating-outlook-form-regions.md).  
  
9. Vyberte jeden nebo více režimů zobrazení, ve kterých má oblast formuláře zobrazit.  
  
     Všechny oblasti formuláře typu se může objevit v kontroly, v režimu vytváření (pro vytváření položek) a v režimu pro čtení (pro zobrazení položek). V podokně čtení může zobrazit i přiléhající, nahrazení a oblasti formuláře nahrazení – to všechno typu.  
  
10. Klikněte na **Další**.  
  
11. Na **identifikování tříd zpráv, které budou zobrazovat tuto oblast formuláře** stránky, vyberte standardní třídy zpráv Outlooku nebo zadejte jména jednoho nebo více vlastní třídy zpráv a potom klikněte na tlačítko **Dokončit**. Další informace najdete v tématu [přidružení oblasti formuláře k třídě zpráv aplikace Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md).  
  
## <a name="see-also"></a>Viz také:  
 [Přístup k oblasti formuláře za běhu](../vsto/accessing-a-form-region-at-run-time.md)   
 [Řešení pro aplikaci Outlook](../vsto/outlook-solutions.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Pokyny pro vytváření oblastí formulářů aplikace Outlook](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [Návod: Návrh oblasti formuláře Outlooku](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Návod: Import oblasti formuláře navržené v aplikaci Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)   
 [Vlastní akce v oblastech formulářů aplikace Outlook](../vsto/custom-actions-in-outlook-form-regions.md)  
