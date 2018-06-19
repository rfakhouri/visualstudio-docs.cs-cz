---
title: Publikování aplikací ClickOnce | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.Options
- Microsoft.VisualStudio.Publish.ClickOnceProvider.PublishWizard.Help
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- ClickOnce applications, publishing
- applications [Visual Studio], ClickOnce deployment
- deploying applications [ClickOnce], publishing ClickOnce applications
ms.assetid: eb6dfe79-f54c-4331-8e36-073688e70973
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c7c6e79f251120b9396d523112c717957817ad5
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
ms.locfileid: "34065299"
---
# <a name="publishing-clickonce-applications"></a>Publikování aplikací ClickOnce
Při publikování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace poprvé, publikovat vlastnosti se dá nastavit pomocí Průvodce publikování. Jen několik vlastností, které jsou k dispozici v Průvodci; všechny ostatní vlastnosti jsou nastavené na výchozí hodnoty.  
  
 Následné publikovat vlastnosti změny na **publikovat** stránku **Návrhář projektu**.  
  
## <a name="publish-wizard"></a>Průvodce publikováním  
 Můžete v Průvodci publikováním základní nastavení konfigurace pro publikování aplikace. To zahrnuje následující vlastnosti publikování:  
  
-   Publikování umístění složky – kde Visual Studio bude kopírovat soubory (místní počítač, síťové sdílené složky, FTP server nebo webu)  
  
-   Umístění složky instalace – kde budou koncoví uživatelé instalovat z (sdílené síťové složce, FTP server, webu, disk CD nebo DVD)  
  
-   Online nebo Offline dostupnost – Pokud koncoví uživatelé mohou přistupovat k aplikaci s nebo bez připojení k síti  
  
-   Četnost – jak často aplikace vyhledává nové aktualizace aktualizace.  
  
 Další informace najdete v tématu [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
## <a name="publish-page"></a>Stránka publikovat  
 **Publikovat** stránky **Návrhář projektu** slouží ke konfiguraci vlastností pro ClickOnce – nasazení. Následující tabulka obsahuje seznam témat  
  
|Název|Popis|  
|-----------|-----------------|  
|[Postupy: Určení cíle kopírování souborů sadou Visual Studio](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)|Popisuje, jak nastavit, kdy sady Visual Studio převádí soubory aplikace a manifesty.|  
|[Postupy: Určení umístění, z něhož mohou instalovat koncoví uživatelé](../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)|Popisuje, jak nastavit umístění, kde uživatelé ke stažení a instalaci aplikace.|  
|[Postupy: Určení offline nebo online režimu instalace ClickOnce](../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)|Popisuje, jak nastavit, jestli aplikace bude k dispozici, offline nebo online.|  
|[Postupy: Nastavení verze publikování ClickOnce](../deployment/how-to-set-the-clickonce-publish-version.md)|Popisuje, jak nastavit ClickOnce **verze publikování** vlastnosti, která určuje, zda aplikace, která jsou publikování budou považovány za aktualizaci.|  
|[Postupy: Automatická inkrementace verze publikování ClickOnce](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)|Popisuje, jak se automaticky zvýší číslo revize **PublishVersion** pokaždé, když publikujete aplikaci.|  
  
 Další informace najdete v tématu [publikovat stránku, Návrhář projektu](../ide/reference/publish-page-project-designer.md)  
  
### <a name="application-files-dialog-box"></a>Dialogové okno soubory aplikace  
 Toto dialogové okno umožňuje zadat, jak jsou soubory v projektu zařazené do kategorie pro publikování, dynamické stahování a aktualizace. Obsahuje tabulku, ve které jsou uvedené soubory projektu, které nejsou ve výchozím nastavení vyloučeny, nebo jež mají skupinu stažení.  
  
 Vyloučit soubory, soubory označit jako datové soubory nebo požadavky a vytvořit skupiny souborů pro podmíněnou instalaci ve Visual Studiu, najdete v části [postup: Určete který souborů k publikování aplikací ClickOnce](../deployment/how-to-specify-which-files-are-published-by-clickonce.md). Datové soubory můžete také označit pomocí Mage.exe. Další informace najdete v tématu [postupy: zahrnutí datového souboru v aplikaci ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
### <a name="prerequisites-dialog-box"></a>Dialogové okno Požadavky  
 Toto dialogové okno určuje požadovaných součástí, které jsou nainstalovány, a také o tom, že jsou nainstalovány. Další informace najdete v tématu [postupy: instalace předpokladů s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md) a [dialogové okno požadavky](../ide/reference/prerequisites-dialog-box.md).  
  
### <a name="application-updates-dialog-box"></a>Dialogové okno aktualizace aplikace  
 Toto dialogové okno určuje, jak by měla instalace aplikace vyhledat aktualizace. Další informace najdete v tématu [postupy: Správa aktualizací pro aplikaci ClickOnce](../deployment/how-to-manage-updates-for-a-clickonce-application.md).  
  
### <a name="publish-options-dialog-box"></a>Publikování dialogové okno Možnosti  
 Dialogové okno Možnosti publikování určuje možnosti nasazení aplikace.  
  
|||  
|-|-|  
|[Postupy: Změna jazyka publikování pro aplikaci ClickOnce](../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)|Popisuje, jak zadat jazykovou verzi odpovídající lokalizované verzi.|  
|[Postupy: Určení názvu úvodní nabídky pro aplikaci ClickOnce](../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)|Popisuje, jak změnit zobrazovaný název pro aplikaci ClickOnce.|  
|[Postupy: Určení obsahu pro technickou podporu](../deployment/how-to-specify-a-link-for-technical-support.md)|Popisuje, jak nastavit **URL podpory** vlastnosti, která identifikuje webové stránky nebo sdílené složky, kde mohou uživatelé získat informace o aplikaci.|  
|[Postupy: Určení adresy URL webu s podporou pro jednotlivé předpoklady v nasazení ClickOnce](../deployment/how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment.md)|Ukázal, jak ručně změnit manifest aplikace zahrnout jednotlivých adres URL podpory pro každý požadavek.|  
|[Postupy: Určení stránky publikování pro aplikaci ClickOnce](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)|Popisuje, jak vygeneruje a publikuje výchozí webovou stránku (publish.htm) spolu s aplikací|  
|[Postupy: přizpůsobení ClickOnce výchozí webové stránky](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)|Popisuje, jak přizpůsobit webovou stránku, který je automaticky generován a publikovaná spolu s aplikací.|  
|[Postupy: Povolení funkce AutoStart pro instalace z média CD](../deployment/how-to-enable-autostart-for-cd-installations.md)|Popisuje, jak povolit automatické tak, aby aplikace ClickOnce se automaticky spustí, když vložení média.|  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Postupy: Vytváření přidružení souborů pro aplikaci ClickOnce](../deployment/how-to-create-file-associations-for-a-clickonce-application.md)|Popisuje postup přidání podpory přípony názvu souboru do aplikace ClickOnce.|  
|[Postupy: Načtení informací řetězce dotazu do online aplikace ClickOnce](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)|Ukazuje, jak získat parametry předané v adrese URL používá ke spouštění aplikací ClickOnce.|  
|[Postupy: Zákaz aktivace adresy URL aplikací ClickOnce pomocí Návrháře](../deployment/how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer.md)|Popisuje, jak chcete vynutit uživatelům spustit aplikaci z **spustit** nabídky pomocí návrháře.|  
|[Postupy: Zákaz aktivace adresy URL aplikací ClickOnce](../deployment/how-to-disable-url-activation-of-clickonce-applications.md)|Popisuje, jak chcete vynutit uživatelům spustit aplikaci z **spustit** nabídky.|  
|[Návod: Stahování sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce pomocí Návrháře](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md)|Vysvětluje, jak stáhnout sestavení aplikace pouze při prvním použití aplikací pomocí návrháře.|  
|[Návod: Stahování sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Vysvětluje, jak stáhnout sestavení aplikace pouze při prvním použití aplikací.|  
|[Návod: Stahování satelitních sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Popisuje, jak označit vaše satelitní sestavení jako volitelné a stáhnout pouze sestavení, klientský počítač potřebuje pro jeho aktuální nastavení jazykové verze.|  
|[Návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)|Vysvětluje, jak pokud chcete nasadit aplikaci ClickOnce pomocí nástroje pro rozhraní .NET Framework.|  
|[Návod: Ruční nasazení aplikace ClickOnce, jež nevyžaduje opětovné podepsání a které zachovává údaje o poskytovateli](../deployment/walkthrough-manually-deploying-a-clickonce-app-no-re-signing-required.md)|Vysvětluje, jak používat nástroje rozhraní .NET Framework pro nasazení aplikace ClickOnce bez opětovné podepisování manifestů.|  
|[Postupy: Konfigurace projektů pro cílové platformy](../ide/how-to-configure-projects-to-target-platforms.md)|Vysvětluje, jak publikovat pro 64bitový procesor změnou **cílový procesor** nebo **Cílová platforma** vlastnost ve vašem projektu.|  
|[Návod: Povolení aplikace ClickOnce ke spuštění na více verzí rozhraní .NET Framework](http://msdn.microsoft.com/en-us/7f4383af-ed87-4853-b4d4-02a3967a5fd9)|Vysvětluje, jak povolit aplikaci ClickOnce k instalaci a spuštění na více verzích rozhraní NET Framework.|  
|[Návod: Vytvoření vlastního instalátoru pro aplikaci ClickOnce](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md)|Vysvětluje, jak vytvořit vlastní instalační program pro instalaci aplikace ClickOnce.|  
|[Postupy: Publikování aplikace WPF s povolenými vizuálními styly](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md)|Obsahuje podrobné pokyny pro řešení chyby, jež se zobrazí při pokusu o publikování aplikace WPF, která má povoleny vizuální styly.|  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Referenční dokumentace technologie ClickOnce](../deployment/clickonce-reference.md)