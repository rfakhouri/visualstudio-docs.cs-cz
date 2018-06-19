---
title: Instalace VSPackages pomocí Instalační služby systému Windows | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- installation [Visual Studio SDK], with Windows Installer
- VSPackages, deploying
ms.assetid: 41d2c72c-0a97-4fcd-b3aa-33a8d3aa962a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6fafebe0dc2bb8e13c99be8b340e7f5663a9930f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31131000"
---
# <a name="installing-vspackages-with-windows-installer"></a>Instalace VSPackages pomocí Instalační služby systému Windows
Integrace do vaší VSPackage [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vyžaduje více než pouhé kopírování souborů na počítači uživatele. Instalační program vaše VSPackage musíte nainstalovat VSPackage a jeho závislých souborů a zaregistrovat a integrovat do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Vaše VSPackage můžete využít výhod funkcí pro integraci například zobrazení na ikonu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] úvodní obrazovky a o dialogové okno.  
  
 Doporučený způsob distribuce vaší VSPackages jsou soubory Instalační služby systému Windows. Snadné použití balíčky Instalační služby systému Windows můžete spustit v jakémkoliv operačním systému Windows nepodporuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Další informace najdete v tématu [Instalační služby systému Windows](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Základní informace o Instalační službě systému Windows](../../extensibility/internals/windows-installer-basics.md)  
 Poskytuje přehled Instalační služby systému Windows.  
  
 [Scénáře instalace balíčku VSPackage](../../extensibility/internals/vspackage-setup-scenarios.md)  
 Popisuje různé způsoby, kterými může podporovat vedle sebe instalace obou vašem VSPackages a [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Vytvoření balíčku Instalační služby systému Windows](../../extensibility/internals/authoring-a-windows-installer-package.md)  
 Poskytuje přehled o obvyklé kroky instalačních programů podle správně nainstalovat a integrovat VSPackages do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Zjištění požadavků na systém](../../extensibility/internals/detecting-system-requirements.md)  
 Popisuje, jak může zjistit, instalační program [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a jeho komponenty a zrušit instalační program, pokud nejsou splněné požadavky VSPackage.  
  
 [Správa komponent](../../extensibility/internals/component-management.md)  
 Popisuje, jak vyvíjet instalační program, který bude uchovávat integritu předchozích verzí produktu.  
  
 [Výběr instalačního adresáře pro balíček VSPackage](../../extensibility/internals/choosing-the-installation-directory-for-a-vspackage.md)  
 Shrnuje možnosti pro vyhledání VSPackages.  
  
 [Registrace balíčku VSPackage](../../extensibility/internals/vspackage-registration.md)  
 Popisuje, jak jsou VSPackages registrované v průběhu instalace a proč automatickou registraci je vhodné.  
  
 [Nasazování typů projektů](../../extensibility/internals/deploying-project-types.md)  
 Popisuje, jak používat nový agregátor typu projektu pro typy projektů spravovaného kódu.  
  
 [Postupy: Vygenerování informací registru pro instalační program ](../../extensibility/internals/how-to-generate-registry-information-for-an-installer.md)  
 Vysvětluje, jak používat RegPkg.exe ke generování manifestu registrace pro spravované VSPackage.  
  
 [Příkazy, které se musí spustit po instalaci](../../extensibility/internals/commands-that-must-be-run-after-installation.md)  
 Vysvětluje, jak spouštět příkazy po instalaci k integraci VSPackages do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Odinstalace balíčku VSPackage pomocí Instalační služby systému Windows](../../extensibility/internals/uninstalling-a-vspackage-with-windows-installer.md)  
 Popisuje kroky, které instalačním programem vaší musíte provést, když uživatelé odinstalovat vaší VSPackage.  