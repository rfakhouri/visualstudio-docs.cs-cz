---
title: Konfigurace počítače pro vývoj řešení pro systém Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, installing tools
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 58458b51115834b5b94e858676ee8039d5894c70
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="configure-a-computer-to-develop-office-solutions"></a>Konfigurace počítače pro vývoj řešení pro systém Office

Pokud chcete vytvořit doplňků VSTO a vlastní nastavení pro Microsoft Office, nainstalujte podporovanou verzi sady Visual Studio, rozhraní .NET Framework a aplikace Microsoft Office.

|Software|Podporované verze|
|--------------|------------------------|
|Visual Studio 2017| Všechny verze **vývoj pro Office/SharePoint** zatížení.|
|.NET Framework|-Rozhraní .NET Framework 4 nebo novější.|
|Aplikace Microsoft Office|<ul><li>Všechny edice sady Office, včetně Office Professional Plus pro Office 365.</li><li>Některé z následujících samostatné aplikace:<br /><br /> <ul><li>Excel</li><li>InfoPath (Office 2013 a Office 2010 pouze)</li><li>Outlook</li><li>PowerPoint</li><li>Projekt</li><li>Visio</li><li>Word</li></ul></li></ul><br /> Visual Basic for Applications (VBA) musí být nainstalován jako součást sady Office. **Důležité:** klikněte na tlačítko spustit verze aplikací Office 2010 nejsou podporovány.|

Instalace podrobné pokyny najdete v tématu [postupy: Konfigurace počítače pro vývoj řešení pro systém Office](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md).

## <a name="if-project-templates-dont-appear-or-they-dont-work-in-visual-studio"></a>Pokud se nezobrazí šablon projektu nebo nemáte fungují v sadě Visual Studio

Pokud instalujete podporovanou verzi sady Visual Studio, rozhraní .NET Framework a aplikace Microsoft Office, ale šablony projektů Office buď nezobrazí v sadě Visual Studio **nový projekt** dialogové okno, nebo se zobrazí chybu při pokusu použít jednu, Zkontrolujte následující:

- Ujistěte se, že máte v počítači nainstalována sada Microsoft Office developer tools.

     Nástroje pro vývojáře Office jsou volitelná komponenta produktu Visual Studio, ale se obvykle instalují automaticky společně s Visual Studio. Pokud instalaci sady Visual Studio můžete přizpůsobit zadáním funkcí, které chcete nainstalovat, ujistěte se, že zvolíte **Microsoft Office Developer Tools** během instalace k instalaci nástroje.

     Abyste měli jistotu, že tyto nástroje jsou nainstalovány, spusťte instalační program sady Visual Studio a zvolte **upravit** tlačítko. Vyberte **Microsoft Office Developer Tools** zaškrtněte políčko a potom vyberte **aktualizace** tlačítko.

- Ujistěte se, že nejsou spuštěné verze systému Office, že se zasílá klikněte na tlačítko spustit. V tématu [postup: Ověřte, zda se aplikace Outlook klikněte na tlačítko spustit aplikaci na počítač](http://msdn.microsoft.com/library/office/ff864733(v=office.14).aspx).

- Ujistěte se, že používáte jenom jedna verze nástroje Microsoft Office.

Pokud budete pokračovat, dochází k potížím, najdete v části [další podpora pro chyby v řešeních pro systém Office](../vsto/additional-support-for-errors-in-office-solutions.md).

## <a name="see-also"></a>Viz také

[Začínáme &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)  
[Postupy: Konfigurace počítače pro vývoj řešení pro systém Office](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)  
[Postupy: instalace sady Visual Studio Tools for Office runtime redistributable](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)  
[Postupy: Primární spolupracující sestavení Office instalace](../vsto/how-to-install-office-primary-interop-assemblies.md)  
[Zadejte dostupné funkce podle aplikace Office a projektu](../vsto/features-available-by-office-application-and-project-type.md)
