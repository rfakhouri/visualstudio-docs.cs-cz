---
title: "Konfigurace počítače pro vývoj řešení pro systém Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, installing tools
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: c3e0ab446cb2aa65d0ec90aea596308ec4dcafec
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="configuring-a-computer-to-develop-office-solutions"></a>Konfigurace počítače pro vývoj řešení pro systém Office
  Pokud chcete vytvořit doplňků VSTO a vlastní nastavení pro Microsoft Office, nainstalujte podporovanou verzi sady Visual Studio, rozhraní .NET Framework a aplikace Microsoft Office.  
  
|Software|Podporované verze|  
|--------------|------------------------|  
|Visual Studio|-   [!INCLUDE[vsPro](../sharepoint/includes/vspro-md.md)]<br />-   [!INCLUDE[vsPreShort](../vsto/includes/vspreshort-md.md)]<br />-   [!INCLUDE[vsUltShort](../vsto/includes/vsultshort-md.md)]**Důležité:** políčko Microsoft Office Developer Tools musíte vybrat během instalace.|  
|.NET Framework|-Rozhraní .NET Framework 4 nebo novější.|  
|Aplikace Microsoft Office|<ul><li>Všechny edice sady Office, včetně Office Professional Plus pro Office 365.</li><li>Některé z následujících samostatné aplikace:<br /><br /> <ul><li>Excel</li><li>InfoPath (Office 2013 a Office 2010 pouze)</li><li>Outlook</li><li>PowerPoint</li><li>Projekt</li><li>Visio</li><li>Word</li></ul></li></ul><br /> Visual Basic for Applications (VBA) musí být nainstalován jako součást sady Office. **Důležité:** klikněte na tlačítko spustit verze aplikací Office 2010 nejsou podporovány.|  
  
 Instalace podrobné pokyny najdete v tématu [postupy: Konfigurace počítače pro vývoj řešení pro Office](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md).  
  
## <a name="if-project-templates-dont-appear-or-they-dont-work-in-visual-studio"></a>Pokud se nezobrazí šablon projektu nebo nemáte fungují v sadě Visual Studio  
 Pokud instalujete podporovanou verzi sady Visual Studio, rozhraní .NET Framework a aplikace Microsoft Office, ale šablony projektů Office buď nezobrazí v sadě Visual Studio **nový projekt** dialogové okno, nebo se zobrazí chybu při pokusu použít jednu, Zkontrolujte následující:  
  
-   Ujistěte se, že máte v počítači nainstalována sada Microsoft Office developer tools.  
  
     Nástroje pro vývojáře Office jsou volitelná komponenta produktu Visual Studio, ale se obvykle instalují automaticky společně s Visual Studio. Pokud instalaci sady Visual Studio můžete přizpůsobit zadáním funkcí, které chcete nainstalovat, ujistěte se, že zvolíte **Microsoft Office Developer Tools** během instalace k instalaci nástroje.  
  
     K zajištění, aby byly nainstalovány tyto nástroje, spusťte instalační program sady Visual Studio a zvolte **upravit** tlačítko. Vyberte **Microsoft Office Developer Tools** zaškrtněte políčko a potom vyberte **aktualizace** tlačítko.  
  
-   Ujistěte se, že nejsou spuštěné verze systému Office, že se zasílá klikněte na tlačítko spustit. V tématu [postup: Ověřte, zda se aplikace Outlook klikněte na tlačítko spustit aplikaci na počítač](http://msdn.microsoft.com/library/office/ff864733(v=office.14).aspx).  
  
-   Ujistěte se, že používáte jenom jedna verze nástroje Microsoft Office.  
  
 Pokud budete pokračovat, dochází k potížím, najdete v části [další podpora pro chyby v řešeních pro systém Office](../vsto/additional-support-for-errors-in-office-solutions.md).  
  
## <a name="see-also"></a>Viz také  
 [Začínáme &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Postupy: Konfigurace počítače pro vývoj řešení pro systém Office](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)   
 [Postupy: instalace sady Visual Studio Tools for Office Runtime Redistributable](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)   
 [Postupy: instalace primární spolupracující sestavení sady Office](../vsto/how-to-install-office-primary-interop-assemblies.md)   
 [Dostupné funkce podle aplikací systému Office a typů projektu](../vsto/features-available-by-office-application-and-project-type.md)  
  
  