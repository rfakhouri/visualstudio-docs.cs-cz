---
title: Publikovat stranu, Návrhář projektu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.PropertyPage
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Project Designer, Publish page
- Publish page in Project Designer
ms.assetid: 153527c6-8b95-4003-8e8e-03a489d0a629
caps.latest.revision: 37
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f135221564583d2d9726bb9fa153840b1328e96f
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65701818"
---
# <a name="publish-page-project-designer"></a>Publikovat stránku, návrhář projektu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

**Publikovat** stránku **Návrháře projektu** slouží ke konfiguraci vlastností pro nasazení ClickOnce.  
  
 Pro přístup **publikovat** stránky, vyberte uzel projektu v **Průzkumníku řešení**a pak klikněte na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrháře projektu** se zobrazí, klikněte na tlačítko **publikovat** kartu.  
  
> [!NOTE]
> Některé vlastnosti ClickOnce je zde popsáno, můžete také nastavit v **PublishWizard**, která je dostupná z **sestavení** nabídek nebo kliknutím **PublishWizard** na toto tlačítko stránka.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Umístění složky pro publikování**  
 Určuje umístění, kde je aplikace publikována. Může být cesta jednotky (`C:\deploy\myapplication`), sdílené složky (`\\server\myapplication`), FTP server (`ftp://ftp.microsoft.com/myapplication`), nebo na web (`http://www.microsoft.com/myapplication`). Všimněte si, že text musí být součástí **umístění pro publikování** pole mohl procházet (**...** ) tlačítko pro práci.  
  
 Ve výchozím nastavení, je umístění pro publikování `http://localhost/<projectname>/` Pokud máte službu IIS nainstalovánu, nebo `publish\` adresáře, pokud nemáte nainstalovanou službu IIS. Pokud váš počítač se systémem Windows Vista, výchozí hodnota je vždy `publish\` adresáře, bez ohledu na to, zda máte nainstalovanou službu IIS.  
  
 **Adresa URL složky instalace**  
 Volitelné. Určuje webové stránky, ke kterému uživatelé přejít k instalaci aplikace. To je nezbytné, jenom když se liší od **umístění pro publikování**, například při publikování aplikace na testovacím serveru.  
  
 **Režim instalace a nastavení**  
 Určuje, zda je aplikace spuštěna přímo z **umístění pro publikování** (když **aplikace je dostupná pouze online** je vybraná) nebo je nainstalován a přidán do **Start**  nabídky a **přidat nebo odebrat programy** položky v **ovládací panely** (když **aplikace je k dispozici také v režimu offline** je vybrána).  
  
 Pro aplikace WPF webového prohlížeče **aplikace je k dispozici také v režimu offline** možnost je zakázána, protože tyto aplikace jsou k dispozici pouze online.  
  
 **Soubory aplikace**  
 Otevře [aplikace souborech – dialogové](https://msdn.microsoft.com/b06dff3a-b87a-4caf-996b-7a4acf8137a8), který se používá k určení, jak a kde jsou nainstalovány jednotlivé soubory.  
  
 **Požadavky**  
 Otevře [dialogové okno požadavky](../../ide/reference/prerequisites-dialog-box.md), který se používá k určení požadovaných součástí, jako je například rozhraní .NET Framework nainstalovat spolu s aplikací.  
  
 **Aktualizace**  
 Otevře [dialogového okna aktualizace aplikace](https://msdn.microsoft.com/8eca8743-8e68-4d04-bfd5-4dc0a9b2934f), který se používá k určení chování aktualizací pro aplikaci. Nejsou k dispozici při **aplikace je dostupná pouze online** zaškrtnuto.  
  
 **Možnosti**  
 Otevře [dialogové okno publikování možnosti](https://msdn.microsoft.com/fd9baa1b-7311-4f9e-8ffb-ae50cf110592), který se používá k určení další pokročilé možnosti publikování.  
  
 **Verze publikování**  
 Nastaví číslo verze publikování pro aplikaci. Při změně číslo verze aplikace publikována jako aktualizace. Každá část verzi publikování (**hlavní**, **menší**, **sestavení**, **revize**) může mít maximální hodnotu 65355 (<xref:System.UInt16.MaxValue>), maximální povolenou <xref:System.Version>.  
  
 Při instalaci více než jednu verzi aplikace s použitím technologie ClickOnce, instalace přesune starší verze této aplikace do složky s názvem Archiv v umístění pro publikování, který zadáte. Archivace dřívějších verzí tímto způsobem udržuje instalační adresář čistý od složek starší verze.  
  
 **Automaticky zvyšovat číslo při každém publikování**  
 Volitelné. Když je vybraná tato možnost (výchozí), **revize** část čísla verze publikování se zvýší o jedna pokaždé, když je aplikace publikována. To způsobí, že aplikace má být publikován jako aktualizace.  
  
 **Průvodce publikováním**  
 Otevře [Průvodce publikováním](https://msdn.microsoft.com/fc6abebd-13d6-48e4-a567-fbc52dad0872). Dokončuje se Průvodce publikováním má stejný účinek jako spuštění **publikovat** příkaz **sestavení** nabídky.  
  
 **Publikovat**  
 Publikuje aplikace s použitím aktuální nastavení. Ekvivalentní **Dokončit** tlačítko **PublishWizard**.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Postupy: Zadejte, kde sada Visual Studio zkopíruje soubory](../../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [Postupy: Zadejte umístění, kde budou koncoví uživatelé instalovat z](../../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)   
 [Postupy: Určení obsahu pro technickou podporu](../../deployment/how-to-specify-a-link-for-technical-support.md)   
 [Postupy: Určení ClickOnce v režimu Offline nebo Online režimu instalace](../../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)   
 [Postupy: Povolení funkce AutoStart pro instalace z disku CD](../../deployment/how-to-enable-autostart-for-cd-installations.md)   
 [Postupy: Nastavení publikování ClickOnce verze](../../deployment/how-to-set-the-clickonce-publish-version.md)   
 [Postupy: Automaticky ClickOnce Inkrementace verze publikování](../../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [Postupy: Určení souborů k publikování aplikací ClickOnce](../../deployment/how-to-specify-which-files-are-published-by-clickonce.md)   
 [Postupy: Instalace předpokladů s aplikací ClickOnce](../../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [Postupy: Správa aktualizací pro aplikaci ClickOnce](../../deployment/how-to-manage-updates-for-a-clickonce-application.md)   
 [Postupy: Změnit jazyka publikování pro aplikaci ClickOnce](../../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)   
 [Postupy: Určení názvu úvodní nabídky pro aplikaci ClickOnce](../../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)   
 [Postupy: Určení stránky publikování pro aplikaci ClickOnce](../../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)   
 [ClickOnce – zabezpečení a nasazení](../../deployment/clickonce-security-and-deployment.md)
