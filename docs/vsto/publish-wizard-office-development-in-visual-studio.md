---
title: Publikování průvodce (vývoj pro Office v sadě Visual Studio)
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.ProjectProperties.PublishWizard
- VST.PublishWizard.Publish.2007System
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], Publish Wizard
- deploying applications [Office development in Visual Studio], Publish Wizard
- Office applications [Office development in Visual Studio], Publish Wizard
- Publish Wizard, Office solutions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2481557d1d75d64b5eb3f52f2755953ca344d323
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692717"
---
# <a name="publish-wizard-office-development-in-visual-studio"></a>Publikování průvodce (vývoj pro Office v sadě Visual Studio)
  Použití **Průvodci publikováním** Pokud chcete kopírovat soubory řešení do zadaného umístění, vytvořte manifestu soubory a vytvořte instalační program.  
  
 K přístupu ke tohoto průvodce na **sestavení** nabídce zvolte **publikovat** *název řešení SolutionName*. Můžete taky Přejít **Průvodci publikováním** z **Průzkumníku řešení**. Otevřete místní nabídku pro uzel projektu a zvolte **publikovat**.  
  
 Každá část níže obsahuje na stránce průvodce.  
  
## <a name="where-do-you-want-to-publish-the-application"></a>Pokud chcete publikovat aplikaci?  
 **Zadejte umístění pro publikování této aplikace**  
 Požadováno. Umístění pro publikování je adresář, kde **Průvodci publikováním** zkopíruje soubory řešení například manifesty, sestavení, dočasný certifikátu a další soubory ze sestavení. Musíte mít oprávnění k zápisu do tohoto adresáře.  
  
 Zadejte umístění jako cesta k disku, sdílené složky, server FTP nebo adresa URL webu, nebo klikněte **Procházet** tlačítko procházení pro umístění. Cesta může být v těchto formátech:  
  
-   Relativní nebo absolutní cesta ve verzi standard systému Windows, jako například formátu *C:\Deploy\MyApplication* nebo *\MyApplication*.  
  
-   Cestu Universal Naming Convention (UNC), jako například  *\\\ServerName\MyApplication\\*.  
  
-   Adresu URL webu lokality, jako například http://www.microsoft.com/MyApplication.  
  
 Ve výchozím umístění pro publikování je *http://localhost/projectname/* Pokud máte nainstalovanou službu IIS, nebo adresáři publish\ v takovém případě ještě nainstalována služba IIS.  
  
> [!NOTE]  
>  Existují další důležité informace, pokud má cílový počítač se systémem Windows Vista. Musíte být správce v počítači Windows Vista použít možnost místní publikovat. Kromě toho výchozí umístění je vždy *publikování\\*  adresář, bez ohledu na to, jestli máte nainstalovanou službu IIS.  
  
## <a name="what-is-the-default-installation-path-on-end-user-computers"></a>Co je výchozí cesty instalace na počítačích koncových uživatelů?  
 Cesta instalace je volitelný. Cesta instalace můžete nastavit později, pokud dáváte přednost. Podrobnosti najdete v tématu [postup: Změňte cestu instalace řešení Office](http://msdn.microsoft.com/en-us/d0eaa07b-2d72-4902-899f-2f9fb165b8fd).  
  
 Instalační cesta je adresář, ze kterého koncový uživatel nainstaluje přizpůsobení. Je také cestu, která řešení bude používat ke kontrole aktualizací. **Průvodci publikováním** Nenasazuje řešení do tohoto umístění, pokud cesta není stejný jako ten, který jste zadali v **zadejte umístění pro publikování této aplikace** pole na předchozí stránce.  
  
 **Z webu.**  
 Zadejte adresu URL, který koncoví uživatelé budou při instalaci řešení.  
  
 **Ze sdílené složky nebo cesty UNC**  
 Zadejte cestu UNC, které koncoví uživatelé budou při instalaci řešení.  
  
 **Z disku CD-ROM nebo DVD-ROM**  
 Tato možnost nevyžaduje, aby instalační cestu.  
  
 Visual Studio není zápis, disk CD nebo DVD. Výstup disku CD nebo DVD musíte zkopírovat ručně.  
  
## <a name="see-also"></a>Viz také:  
 [Nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Publikovat stránku, Návrhář projektu &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/publish-page-project-designer-office-development-in-visual-studio.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
  
  