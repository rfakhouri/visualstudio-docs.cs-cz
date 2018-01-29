---
title: "Publikovat stránku, Návrhář projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.PropertyPage
helpviewer_keywords:
- Project Designer, Publish page
- Publish page in Project Designer
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a3eee4abda5783707231332022e1f3f24728e7cc
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="publish-page-project-designer"></a>Publikovat stránku, návrhář projektu
**Publikovat** stránky **Návrhář projektu** slouží ke konfiguraci vlastností pro ClickOnce – nasazení.  
  
 Pro přístup k **publikovat** vyberte uzel projektu v **Průzkumníku řešení**a pak klikněte na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrhář projektu** se zobrazí, klikněte na tlačítko **publikovat** kartě.  
  
> [!NOTE]
>  Některé vlastnosti ClickOnce popsané v tomto poli může být nastavena v **PublishWizard**, k dispozici **sestavení** nabídky nebo kliknutím **PublishWizard** na toto tlačítko stránka.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Publikování umístění složky**  
 Určuje umístění, kde je aplikace publikována. Může být cesta jednotky (`C:\deploy\myapplication`), sdílené složky (`\\server\myapplication`), FTP server (`ftp://ftp.microsoft.com/myapplication`), nebo na web (`http://www.microsoft.com/myapplication`). Všimněte si, že text musí být součástí **umístění pro publikování** pole v pořadí pro Procházet (**...** ) tlačítko pracovat.  
  
 Ve výchozím umístění pro publikování je `http://localhost/<projectname>/` Pokud máte službu IIS nainstalovánu, nebo `publish\` adresáře, pokud nemáte nainstalovanou službu IIS. Pokud váš počítač se systémem Windows Vista, výchozí hodnota je vždy `publish\` adresář, bez ohledu na to, jestli máte nainstalovanou službu IIS.  
  
 **Adresy URL instalace složky**  
 Volitelné. Určuje webu, ke kterému uživatelé instalovat aplikace. To je nezbytné, pouze pokud se liší od **umístění pro publikování**, například když je aplikace publikována na pracovní server.  
  
 **Režim instalace a nastavení**  
 Určuje, zda je aplikace spuštěna přímo z **umístění pro publikování** (při **aplikace je k dispozici pouze online** je vybraná) nebo je nainstalována a přidat do **spustit**  nabídky a **přidat nebo odebrat programy** položky v **ovládací panely** (když **aplikace je k dispozici také offline** je vybraný).  
  
 Pro WPF aplikace webového prohlížeče **aplikace je k dispozici také offline** možnost je zakázána, protože takové aplikace jsou k dispozici pouze online.  
  
 **Soubory aplikace**  
 Otevře dialogové okno souborů aplikace, které slouží k určení, jak a kde jsou nainstalovány jednotlivé soubory.  
  
 **Požadavky**  
 Otevře dialogové okno požadavky, které slouží k určení požadovaných součástí, jako je rozhraní .NET Framework, společně s aplikace nainstalována.  
  
 **Updates**  
 Otevře dialogové okno aktualizace aplikace, které slouží k určení chování aktualizací pro danou aplikaci. Nejsou k dispozici při **aplikace je k dispozici pouze online** je vybrána.  
  
 **Možnosti**  
 Otevře dialogové okno Možnosti publikování, který slouží k určení dalších upřesňujících možností publikování.  
  
 **Verze publikování**  
 Nastaví číslo verze publikování pro aplikaci. Při změně číslo verze aplikace publikována jako aktualizace. Jednotlivých součástí verzi publikování (**hlavní**, **menší**, **sestavení**, **revize**) může mít maximální hodnota je 65355 (<xref:System.UInt16.MaxValue>), maximální povolenou <xref:System.Version>.  
  
 Při instalaci více než jedna verze aplikace s použitím technologie ClickOnce, instalaci starší verze aplikace přesune do složky s názvem Archiv v umístění pro publikování, který určíte. Archivace dřívější verze tímto způsobem udržuje instalační adresář vymazat složek ze starší verze.  
  
 **Zvýšit automaticky revizi při každém publikování**  
 Volitelné. Pokud je vybraná tato možnost (výchozí), **revize** součástí číslo verze publikování se zvýší o jeden pokaždé, když je aplikace publikována. To způsobí, že aplikace má být publikován jako aktualizace.  
  
 **Průvodce publikováním**  
 Otevře Průvodce publikováním. Probíhá dokončování Průvodce Publikovat má stejný účinek jako spuštěná **publikovat** příkaz na **sestavení** nabídky.  
  
 **Nyní publikování**  
 Publikuje aplikace pomocí aktuální nastavení. Ekvivalentní **Dokončit** v tlačítko **PublishWizard**.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../../deployment/publishing-clickonce-applications.md)   
 [Postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Postupy: Zadejte, kde zkopíruje soubory v sadě Visual Studio](../../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [Postupy: určení umístění, kde budou koncoví uživatelé instalovat z](../../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)   
 [Postupy: určení odkazu na technickou podporu](../../deployment/how-to-specify-a-link-for-technical-support.md)   
 [Postupy: Zadejte ClickOnce do režimu Offline nebo Online režimu instalace](../../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)   
 [Postupy: povolení funkce AutoStart pro instalace z disku CD](../../deployment/how-to-enable-autostart-for-cd-installations.md)   
 [Postupy: verze publikování ClickOnce sady](../../deployment/how-to-set-the-clickonce-publish-version.md)   
 [Postupy: automaticky verze publikování ClickOnce přírůstku](../../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [Postupy: určení souborů k publikování aplikací ClickOnce](../../deployment/how-to-specify-which-files-are-published-by-clickonce.md)   
 [Postupy: instalace předpokladů s aplikací ClickOnce](../../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [Postupy: Správa aktualizací pro aplikaci ClickOnce](../../deployment/how-to-manage-updates-for-a-clickonce-application.md)   
 [Postupy: Změna jazyka publikování pro aplikaci ClickOnce](../../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)   
 [Postupy: určení názvu úvodní nabídky pro aplikaci ClickOnce](../../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)   
 [Postupy: určení stránky publikování pro aplikaci ClickOnce](../../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)   
 [ClickOnce – zabezpečení a nasazení](../../deployment/clickonce-security-and-deployment.md)