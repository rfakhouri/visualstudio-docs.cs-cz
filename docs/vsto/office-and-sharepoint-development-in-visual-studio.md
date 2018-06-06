---
title: Office a vývoj pro SharePoint v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], about developing applications
- Office development in Visual Studio
- Office projects
- Visual Studio Tools for Office, see Office development in Visual Studio
- Office applications [Office development in Visual Studio]
- Office Business Applications
- applications [Office development in Visual Studio]
- programming [Office development in Visual Studio]
- VSTO, see Office development in Visual Studio
- Office, development with Visual Studio
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c7bd0f38d413fbd3d809773a124699e0e883287d
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572163"
---
# <a name="office-and-sharepoint-development-in-visual-studio"></a>Vývoj pro Office a SharePoint v sadě Visual Studio
  Můžete rozšířit vytvoření jednoduché aplikace Microsoft Office a SharePoint nebo doplňku, uživatelé stáhnout z [Office úložiště](https://store.office.com/) nebo organizační katalogu nebo vytvořením řešení založené na rozhraní .NET Framework, kterou můžou uživatelé instalovat na počítač.  
  
 V tomto tématu:  
  
-   [Vytváření doplňků pro Office a SharePoint](#Apps)  
  
-   [Vytvoření doplňku VSTO](#Add-ins)  
  
-   [Vytvoření řešení služby SharePoint](#Solutions)  
  
##  <a name="Apps"></a> Vytváření doplňků pro Office a SharePoint  
 Office 2013 a SharePoint 2013 zavést nový doplňku model, který vám pomůže vytvořit, distribuci a monetizovat doplňky, které rozšiřují Office a SharePoint.  Tyto doplňky můžete spustit v Office nebo SharePoint Online, a mohou uživatelé komunikovat s nimi z mnoha zařízení.  
  
 Zjistěte, jak používat nové [model doplňku Office](https://msdn.microsoft.com/library/office/jj220082.aspx) rozšíření prostředí Office pro uživatele.  
  
 Tyto doplňky mají velmi malé pracovníkům ve srovnání s doplňků VSTO a řešení, a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  Abyste mohli začít, použijte Office Developer Tools v sadě Visual Studio nebo lightweight webový nástroj označován kódovým Napa Office 365 vývojovými nástroji, které umožňuje vytváření projektů, napsat kód a spusťte doplňky v prohlížeči.  
  
 ![Aplikace pro systém Office a SharePoint konceptuálního modelu](../vsto/media/officeandsharepointapps2015.png "aplikací pro systém Office a SharePoint konceptuálního modelu")  
  
### <a name="build-an-office-add-in"></a>Sestavení doplňku Office  
 K rozšíření funkčnosti sady Office, sestavení doplňku Office. Je v podstatě webovou stránku, který je hostován v aplikaci Office Excel, Word, Outlook a PowerPoint. Aplikace můžete přidat funkce na dokumenty, listy, e-mailové zprávy, události, prezentace a projekty.  
  
 Aplikace v úložišti Office můžete prodeje.  [Office úložiště](https://store.office.com/) usnadňuje monetizovat doplňků, Správa aktualizací a sledování telemetrie. Můžete také publikovat aplikace uživatelům prostřednictvím katalogu aplikací ve službě SharePoint nebo na serveru Exchange Server.  
  
 Následující aplikace pro Office zobrazuje data listu v mapy Bing.  
  
 ![Obsahu aplikace pro Office](../vsto/media/appforoffice.png "obsahu aplikace pro Office")  
  
 **Víc se uč**  
  
|Chcete-li|Další informace naleznete v tématu|  
|--------|---------|  
|Další informace o doplňcích Office a následně vytvořit jednu.|[Doplňky sady Office](http://msdn.microsoft.com/office/dn448457)|  
|Porovnání způsobů, ve kterém můžete rozšířit Office a rozhodnout, zda byste měli používat aplikaci nebo doplňku Office.|[Plán pro Office doplňků VSTO a VBA](http://blogs.msdn.com/b/officeapps/archive/2013/06/18/roadmap-for-apps-for-office-vsto-and-vba.aspx)|  
  
### <a name="build-a-sharepoint-add-in"></a>Sestavení doplněk služby SharePoint  
 Pokud chcete rozšířit služby SharePoint pro vaše uživatele, sestavte přidat do služby SharePoint. Je v podstatě malé, snadné použití, samostatné aplikace, která řeší potřebu uživatele nebo firmy.  
  
 Aplikace můžete prodeje pro SharePoint v [Office úložiště](https://store.office.com/). Můžete také publikovat vaše doplněk uživatelům prostřednictvím k katalogu ve službě SharePoint.  Vlastníci webu můžete nainstalovat, upgradu a odinstalaci tohoto doplňku na svých webech služby SharePoint, bez pomoci serveru farmy nebo správce kolekce webů.  
  
 Tady je příklad aplikace pro službu SharePoint, která pomáhá spravovat obchodní kontakty uživatele.  
  
 ![Obchodní kontaktujte správce aplikace pro službu SharePoint](../vsto/media/appforsharepoint.png "obchodní kontaktujte správce aplikace pro službu SharePoint")  
  
 **Víc se uč**  
  
|Chcete-li|Další informace naleznete v tématu|  
|--------|---------|  
|Další informace o doplňcích služby SharePoint a následně vytvořit jednu.|[Doplňky služby SharePoint](https://msdn.microsoft.com/library/office/fp179930.aspx)|  
|Porovnání doplňky pro službu SharePoint s tradiční řešení služby SharePoint.|[SharePoint doplňky ve srovnání s řešení služby SharePoint](http://msdn.microsoft.com/library/office/jj163114.aspx)|  
|Vyberte, zda chcete vytvořit doplněk SharePoint nebo řešení služby SharePoint.|[Rozhodněte, mezi doplňky SharePoint a řešení služby SharePoint](https://msdn.microsoft.com/library/office/jj163114.aspx)|
  
##  <a name="Add-ins"></a> Vytvoření doplňku VSTO  
 Vytvořte doplňku VSTO pro Office 2007 nebo Office 2010 nebo rozšířit Office 2013 a Office 2016 dále, než je možné pomocí doplňků Office. Doplňků VSTO spustit pouze na ploše. Uživatelé mají k instalaci doplňků VSTO, tak, aby obvykle obtížnější k nasazení a podporu.  Ale tohoto doplňku VSTO dá integrovat přesněji Office. Například ho přidejte karet a ovládacích prvků na pásu karet Office a provést pokročilé automatizace například slučování dokumenty nebo úprava grafy. Můžete využít rozhraní .NET Framework a interakci s objekty Office pomocí jazyka C# a Visual Basic.  
  
 Tady je příklad můžete provést co doplňku VSTO. Doplňku VSTO přidá do aplikace PowerPoint ovládacích prvků pásu karet, vlastního podokna úloh a dialogové okno.  
  
 ![Řešení doplňku PowerPoint](../vsto/media/powerpointaddin.png "PowerPoint doplňku řešení")  
  
 **Víc se uč**  
  
|Chcete-li|Číst|  
|--------|----------|  
|Porovnání způsobů, ve kterém můžete rozšířit Office a rozhodnout, zda byste měli používat doplňku VSTO nebo doplňku Office.|[Plán pro Office doplňků VSTO a VBA](http://blogs.msdn.com/b/officeapps/archive/2013/06/18/roadmap-for-apps-for-office-vsto-and-vba.aspx)|  
|Vytvoření doplňku VSTO.|[Doplňků VSTO sestavení pomocí sady Visual Studio](https://msdn.microsoft.com/library/jj620922.aspx)|  
  
##  <a name="Solutions"></a> Vytvoření řešení služby SharePoint  
 Vytvořte řešení služby SharePoint cílové SharePoint Foundation 2010 a SharePoint Server 2010 nebo SharePoint 2013 a SharePoint 2016 rozšířit způsoby dále, než je možné pomocí doplňku služby SharePoint.  
  
 Řešení služby SharePoint vyžadují místní servery ve farmě služby SharePoint. Správci musí nainstalovat, a protože řešení provést ve službě SharePoint, mohou ovlivnit výkon serveru. Řešení však poskytuje hlubší přístup k objektům služby SharePoint. Navíc při sestavování řešení služby SharePoint, můžete využít rozhraní .NET Framework a interakci s objekty služby SharePoint pomocí jazyka C# a Visual Basic.  
  
 **Víc se uč**  
  
|Chcete-li|Další informace naleznete v tématu|  
|--------|---------|  
|Porovnání řešení služby SharePoint s doplňky služby SharePoint.|[SharePoint doplňky ve srovnání s řešení služby SharePoint](http://msdn.microsoft.com/library/office/jj163114.aspx)|  
|Vytvořte řešení služby SharePoint.|[Vytvoření řešení služby SharePoint](../sharepoint/create-sharepoint-solutions.md)|  
  
  
