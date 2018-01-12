---
title: "Přizpůsobení pásu karet pro aplikaci Outlook | Microsoft Docs"
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
- Inspectors [Office development in Visual Studio]
- Outlook [Office development in Visual Studio], Ribbon
- customizing the Ribbon, about customizing the Ribbon
- custom Ribbon, about customizing the Ribbon
- Ribbon [Office development in Visual Studio], Outlook
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3a7ed84f9eea6c4301f0fe4882d63522df2975f3
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="customizing-a-ribbon-for-outlook"></a>Přizpůsobení pásu karet pro aplikaci Outlook
  Při přizpůsobování na pásu karet v aplikaci Microsoft Office Outlook, musíte zvážit, kde se zobrazí vaše vlastní pás karet v aplikaci. Outlook se zobrazí na pásu karet v hlavní aplikaci uživatelské rozhraní (UI) a v systému windows, které se otevřou při uživatelé provádět určité úlohy, jako je například vytváření e-mailových zpráv. Tyto aplikace windows jsou pojmenované kontroly.  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak I: použít Návrháře pásu karet k přizpůsobení pásu karet v aplikaci Outlook?](http://go.microsoft.com/fwlink/?LinkID=130312).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="adding-a-custom-ribbon-to-the-main-application-ui"></a>Přidání vlastní pás karet do hlavní aplikace uživatelského rozhraní  
 Hlavní aplikace uživatelského rozhraní v aplikaci Outlook se nazývá Průzkumník. Pokud používáte **pásu karet (vizuálního návrháře)** položek, můžete přidat pásu karet do Průzkumníka kliknutím **RibbonType** vlastnost pásu karet **vlastnosti** okno, a potom vyberete **Microsoft.Outlook.Explorer**.  
  
## <a name="assigning-a-ribbon-to-an-inspector"></a>Přiřazení k kontrolor pásu karet  
 Identifikujete inspector, který chcete přizpůsobit zadáním pásu karet typ, který odpovídá třídu zpráv pro funkci Kontrola.  
  
 Pokud používáte **pásu karet (vizuálního návrháře)** položky, klikněte na tlačítko **RibbonType** vlastnost pásu karet v **vlastnosti** a pak vyberte okně jeden nebo více ID z pásu karet seznam hodnot.  
  
 Můžete přidat více než jeden pásu karet do projektu. Pokud více než jeden pásu karet sdílí ID pásu karet, přepíše metodu CreateRibbonExtensibilityObject v `ThisAddin` třída projektu k určení, které pásu karet zobrazíte v době běhu. Další informace najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md). Další informace o jednotlivých typech pásu karet, najdete v článku na technické [přizpůsobení pásu karet v aplikaci Outlook 2007](http://msdn.microsoft.com/en-us/946e97ea-f556-4e84-8fac-01cd9214e170).  
  
## <a name="specifying-the-ribbon-type-by-using-ribbon-xml"></a>Určení typu pásu karet pomocí kódu XML pásu karet  
 Pokud používáte **pásu karet (XML)** položky, zkontrolujte hodnotu *ribbonID* parametr ve <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> metoda a vraťte se na příslušné pásu karet.  
  
 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> Metoda je automaticky generován Visual Studio v souboru kódu pásu karet. *RibbonID* parametr je řetězec, který identifikuje Explorer nebo určitý typ inspector. Úplný seznam možných hodnot *ribbonID* parametr, najdete v článku na technické [přizpůsobení pásu karet v aplikaci Outlook 2007](http://msdn.microsoft.com/en-us/946e97ea-f556-4e84-8fac-01cd9214e170).  
  
 Následující příklad kódu ukazuje, jak zobrazit vlastní pouze v pásu karet `Microsoft.Outlook.Mail.Compose` inspector. Toto je inspector, které se otevře, když uživatel vytvoří novou e-mailová zpráva. Na pásu karet k zobrazení je uveden v `GetResourceText()` metodu, která se generuje ve **pásu karet** třída. Další informace o **pásu karet** třídy najdete v tématu [XML karet](../vsto/ribbon-xml.md).  
  
 [!code-csharp[Trin_RibbonOutlookBasic#1](../vsto/codesnippet/CSharp/Trin_RibbonOutlookBasic/Ribbon1.cs#1)]
 [!code-vb[Trin_RibbonOutlookBasic#1](../vsto/codesnippet/VisualBasic/Trin_RibbonOutlookBasic/Ribbon1.vb#1)]  
  
## <a name="see-also"></a>Viz také  
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Pás karet – XML](../vsto/ribbon-xml.md)  
  
  