---
title: "Přizpůsobení pásu karet pro aplikaci InfoPath | Microsoft Docs"
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
- InfoPath [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], InfoPath
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 40cf51fce578540a5ea27a96e3482e5d7f906754
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="customizing-a-ribbon-for-infopath"></a>Přizpůsobení pásu karet pro aplikaci InfoPath
  Při přizpůsobování na pásu karet v aplikaci Microsoft Office InfoPath, musíte zvážit, kde se zobrazí vaše vlastní pás karet v aplikaci. [!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)]můžete zobrazit na pásu karet v následující tři typy oken aplikace InfoPath:  
  
-   Windows, který zobrazí formulář šablonu, která je otevřen v režimu návrhu.  
  
-   Windows, který zobrazí formulář, který je založený na šabloně formuláře.  
  
-   Okno náhledu.  
  
 **Platí pro:** informace v tomto tématu se vztahují na projekty doplňku VSTO pro aplikaci InfoPath 2010. Další informace najdete v tématu [dostupné funkce podle aplikace Office a typu projektu](../vsto/features-available-by-office-application-and-project-type.md).  
  
 Uživatelé a návrhářů, otevřete šablonu formuláře v režimu návrhu, jak upravit vzhled a rozložení šablony. Uživatelé otevřít formuláře, které jsou na základě v šabloně formuláře přidání obsahu.  
  
 Okno náhledu tisku umožňuje Designer a uživatelé náhled na stránkách formuláře nebo šablony formuláře dříve, než budou tisknout.  
  
> [!NOTE]  
>  **AddIns** karta nezobrazí v okně Náhled. Pokud chcete vlastní karty zobrazí v okně Náhled, ujistěte se, že **OfficeId** vlastnost karty není nastavena na **TabAddIns**.  
  
 Musíte zadat typ pásu karet každý okna, ve kterém chcete, aby vaše pásu karet se objeví.  
  
## <a name="specifying-the-ribbon-type-in-the-ribbon-designer"></a>Určení typu pásu karet v Návrháři pásu karet  
 Pokud používáte **pásu karet (vizuálního návrháře)** položky, klikněte na tlačítko **RibbonType** vlastnost pásu karet v **vlastnosti** okno a pak vyberte některé z ID pásu karet popsané v následující tabulce.  
  
|ID pásu karet|Okno, ve kterém se zobrazí na pásu karet při spuštění projektu|  
|---------------|---------------------------------------------------------------------|  
|**Microsoft.InfoPath.Designer**|Windows, který zobrazí formulář šablonu, která je otevřen v režimu návrhu.|  
|**Microsoft.InfoPath.Editor**|Windows, který zobrazí formulář, který je založený na šabloně formuláře.|  
|**Microsoft.InfoPath.PrintPreview**|Okno náhledu.|  
  
 Můžete přidat více než jeden pásu karet do projektu. Pokud více než jeden pásu karet sdílet ID pásu karet, přepíše metodu CreateRibbonExtensibilityObject v `ThisAddin` třída projektu k určení které pásu karet zobrazíte v době běhu. Další informace najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
## <a name="specifying-the-ribbon-type-by-using-ribbon-xml"></a>Určení typu pásu karet pomocí kódu XML pásu karet  
 Pokud používáte **pásu karet (XML)** položky, zkontrolujte hodnotu *ribbonID* parametr ve <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> metoda a vraťte se na příslušné pásu karet.  
  
 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> Metoda je automaticky generován Visual Studio v souboru kódu pásu karet. *RibbonID* parametr je řetězec, který určuje typ okna InfoPath, který otevírá.  
  
 Následující příklad kódu ukazuje, jak zobrazit vlastní pás karet pouze v okně, které se zobrazí šablony formuláře v režimu návrhu. Na pásu karet k zobrazení je uveden v `GetResourceText()` metoda, která se generují ve třídě pásu karet. Další informace o třídě pásu karet najdete v tématu [XML karet](../vsto/ribbon-xml.md).  
  
 [!code-csharp[Trin_RibbonInfoPathBasic#1](../vsto/codesnippet/CSharp/myinfopathproject/ribbon.cs#1)]
 [!code-vb[Trin_RibbonInfoPathBasic#1](../vsto/codesnippet/VisualBasic/myinfopathproject/ribbon.vb#1)]  
  
## <a name="see-also"></a>Viz také  
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Pás karet – XML](../vsto/ribbon-xml.md)  
  
  