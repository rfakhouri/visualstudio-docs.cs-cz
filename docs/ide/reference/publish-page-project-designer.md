---
title: Publikovat stránku, návrhář projektu
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.PropertyPage
helpviewer_keywords:
- Project Designer, Publish page
- Publish page in Project Designer
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: aa33f3adc4fe05bd0df5c24bcb1fa769f93682cc
ms.sourcegitcommit: 85d66dc9fea3fa49018263064876b15aeb6f9584
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2019
ms.locfileid: "68461643"
---
# <a name="publish-page-project-designer"></a>Publikovat stránku, návrhář projektu

Stránka **publikovat** v **Návrháři projektu** se používá ke konfiguraci vlastností pro nasazení ClickOnce.

 Pro přístup ke stránce **publikovat** vyberte uzel projektu v **Průzkumník řešení**a potom v nabídce **projekt** klikněte na **vlastnosti**. Když se zobrazí **Návrhář projektu** , klikněte na kartu **publikovat** .

> [!NOTE]
> Některé vlastnosti ClickOnce popsané tady lze také nastavit v **PublishWizard**, k dispozici v nabídce **sestavení** nebo kliknutím na tlačítko **PublishWizard** na této stránce.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

 **Umístění složky pro publikování**

 Určuje umístění, kde je aplikace publikována. Může se jednat o cestu k`C:\deploy\myapplication`jednotce (), sdílenou`\\server\myapplication`složku () nebo server FTP (`ftp://ftp.microsoft.com/myapplication`). Všimněte si, že text musí být přítomen v poli **umístění pro publikování** , aby tlačítko Procházet ( **...** ) fungovalo.

 **Adresa URL instalační složky**

 Volitelné. Určuje web, na který uživatelé přejdou instalovat aplikaci. To je nezbytné jenom v případě, že se liší od **umístění pro publikování**, například při publikování aplikace na přípravném serveru.

 **Režim instalace a nastavení**

 Určuje, zda je aplikace spuštěna přímo z **umístění publikování** (Pokud je **aplikace dostupná pouze online** ), nebo je nainstalována a přidána do nabídky **Start** a do položky **Přidat nebo odebrat programy** v části **Ovládací panely** (Pokud je **aplikace dostupná také v režimu offline** ).

 Pro aplikace webového prohlížeče WPF **je aplikace k dispozici offline** a možnost je zakázána, protože tyto aplikace jsou k dispozici pouze online.

 **Soubory aplikace**

 Otevře dialogové okno soubory aplikace, které slouží k určení toho, jak a kde jsou jednotlivé soubory nainstalovány.

 **Požadavky**

 Otevře dialogové okno požadavky, které se používá k určení požadovaných součástí, jako je například .NET Framework, aby se nainstalovaly společně s aplikací.

 **Aktualizace**

 Otevře dialogové okno aktualizace aplikace, které slouží k určení chování aktualizace pro aplikaci. Tato možnost není dostupná, pokud **je aplikace dostupná jenom online** .

 **Možnosti**

 Otevře dialogové okno Možnosti publikování, které slouží k určení dalších pokročilých možností publikování.

 **Verze publikování**

 Nastaví číslo verze publikování pro aplikaci. Když se změní číslo verze, aplikace se publikuje jako aktualizace. Každá část verze publikování (**Hlavní**, podverze , **sestavení**, **Revize**) může mít maximální hodnotu 65355<xref:System.UInt16.MaxValue> <xref:System.Version>(), což je maximální povolený.

 Při instalaci více než jednu verzi aplikace s použitím technologie ClickOnce, instalace přesune starší verze této aplikace do složky s názvem Archiv v umístění pro publikování, který zadáte. Archivace dřívějších verzí tímto způsobem udržuje instalační adresář čistý od složek starší verze.

 **Automaticky zvyšovat revize při každém publikování**

 Volitelné. Pokud je vybrána tato možnost (výchozí nastavení), část **Revize** čísla verze publikování se zvýší o jednu pokaždé, když je aplikace publikována. To způsobí, že se aplikace publikuje jako aktualizace.

 **Průvodce publikováním**

 Otevře Průvodce publikováním. Dokončení Průvodce publikováním má stejný účinek jako spuštění příkazu **publikovat** v nabídce **sestavení** .

 **Publikovat hned**

 Publikuje aplikaci pomocí aktuálního nastavení. Odpovídá tlačítku **Dokončit** v **PublishWizard**.

## <a name="see-also"></a>Viz také:

- [Publikování aplikací ClickOnce](../../deployment/publishing-clickonce-applications.md)
- [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
- [Postupy: Určení cíle kopírování souborů sadou Visual Studio](../../deployment/how-to-specify-where-visual-studio-copies-the-files.md)
- [Postupy: Určení umístění, odkud budou koncoví uživatelé instalovat](../../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)
- [Postupy: Zadání odkazu na technickou podporu](../../deployment/how-to-specify-a-link-for-technical-support.md)
- [Postupy: Určení offline nebo online režimu instalace ClickOnce](../../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)
- [Postupy: Povolení funkce AutoStart při instalaci z disku CD](../../deployment/how-to-enable-autostart-for-cd-installations.md)
- [Postupy: Nastavení verze publikování ClickOnce](../../deployment/how-to-set-the-clickonce-publish-version.md)
- [Postupy: Automatická inkrementace verze publikování ClickOnce](../../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)
- [Postupy: Určení souborů k publikování aplikací ClickOnce](../../deployment/how-to-specify-which-files-are-published-by-clickonce.md)
- [Postupy: Instalace nezbytných součástí aplikace ClickOnce](../../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)
- [Postupy: Správa aktualizací aplikace ClickOnce](../../deployment/how-to-manage-updates-for-a-clickonce-application.md)
- [Postupy: Změna jazyka publikované aplikace ClickOnce](../../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)
- [Postupy: Zadání názvu úvodní nabídky aplikace ClickOnce](../../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)
- [Postupy: Zadání stránky pro publikování aplikace ClickOnce](../../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)
- [ClickOnce – zabezpečení a nasazení](../../deployment/clickonce-security-and-deployment.md)
