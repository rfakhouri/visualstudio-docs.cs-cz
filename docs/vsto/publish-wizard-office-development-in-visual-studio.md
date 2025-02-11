---
title: Průvodce publikováním (vývoj pro Office v sadě Visual Studio)
ms.date: 02/02/2017
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7879ad7cf18c3d09fddbab3923296e0896688af9
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63447069"
---
# <a name="publish-wizard-office-development-in-visual-studio"></a>Průvodce publikováním (vývoj pro Office v sadě Visual Studio)
  Použití **Průvodce publikováním** Pokud chcete zkopírovat soubory řešení do zadaného umístění, vytvořte soubory manifestu a vytvoření instalačního programu.

 Pro přístup k tohoto průvodce na **sestavení** nabídce zvolte **publikovat** *SolutionName*. Se dá dostat taky **Průvodce publikováním** z **Průzkumníka řešení**. Otevřete místní nabídku pro uzel projektu a klikněte na tlačítko **publikovat**.

 Každá část níže popisuje stránce průvodce.

## <a name="where-do-you-want-to-publish-the-application"></a>Pokud chcete publikovat aplikaci?
 **Zadejte umístění pro publikování této aplikace** vyžaduje. Umístění pro publikování je adresář, ve kterém **Průvodce publikováním** zkopíruje soubory řešení, jako je například manifesty, sestavení, dočasný certifikát a dalších souborů ze sestavení. Musíte mít přístup pro zápis do tohoto adresáře.

 Zadejte umístění jako cesta k disku, sdílené složky, FTP nebo adresa URL webu, nebo klikněte na tlačítko **Procházet** tlačítko Procházet pro umístění. Cesta může být v těchto formátů:

- Relativní nebo absolutní cesta ve standardním Windows, například formátování *C:\Deploy\MyApplication* nebo *\MyApplication*.

- Cestu (Universal Naming Convention), jako například  *\\\ServerName\MyApplication\\* .

- Adresa URL webového serveru, jako http://www.microsoft.com/MyApplication.

  Ve výchozím nastavení, je umístění pro publikování *http://localhost/projectname/* Pokud máte nainstalovanou službu IIS, nebo adresáři publish\ Pokud tak učiníte nebyla nainstalována služba IIS.

> [!NOTE]
> Pokud cílový počítač se systémem Windows Vista některé další aspekty. Musíte být správcem počítači se systémem Windows Vista možnost místního publikování. Kromě toho výchozí umístění je vždy *publikovat\\*  adresáře, bez ohledu na to, zda máte nainstalovanou službu IIS.

## <a name="what-is-the-default-installation-path-on-end-user-computers"></a>Co je výchozí instalační cesta na počítačích koncových uživatelů?
 Cesta instalace je volitelné. Instalační cesta můžete nastavit později, pokud dáváte přednost. Podrobnosti najdete v tématu [jak: Změnit cestu instalace řešení pro Office](https://msdn.microsoft.com/d0eaa07b-2d72-4902-899f-2f9fb165b8fd).

 Cesta instalace je adresář, ze kterého koncový uživatel nainstaluje vlastního nastavení. Je také cestu pro toto řešení bude používat ke kontrole aktualizací. **Průvodce publikováním** Nenasazuje řešení do tohoto umístění, pokud cesta není stejný jako ten, který jste zadali v **zadejte umístění pro publikování této aplikace** pole na předchozí stránce.

 **Z webu** zadejte adresu URL, kterou budou koncoví uživatelé provést instalaci řešení.

 **Z sdílenou jednotku UNC cestu nebo soubor** zadejte cestu UNC, která budou koncoví uživatelé provést instalaci řešení.

 **Z disku CD-ROM nebo DVD-ROM** tato možnost nevyžaduje, aby instalační cestu.

 Visual Studio není pracovní tempo CD nebo DVD. Výstup na disk CD nebo DVD musíte zkopírovat ručně.

## <a name="see-also"></a>Viz také:
- [Nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md)
- [Publikovat stranu, Návrhář projektu &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/publish-page-project-designer-office-development-in-visual-studio.md)
- [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)
