---
title: Instalace balíčků VSPackage pomocí Instalační služby systému Windows | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- installation [Visual Studio SDK], with Windows Installer
- VSPackages, deploying
ms.assetid: 41d2c72c-0a97-4fcd-b3aa-33a8d3aa962a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 94dcb85e3cfef9c44cb8e88720f53c296f8bf997
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66349853"
---
# <a name="installing-vspackages-with-windows-installer"></a>Instalace balíčků VSPackage pomocí Instalační služby systému Windows
Integrace do vaší VSPackage [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vyžaduje více než pouhé kopírování souborů na počítači uživatele. Instalační program vašeho balíčku VSPackage musíte nainstalovat sady VSPackage a jeho závislých souborů a zaregistrovat a integrovat je do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Vaše VSPackage můžete využít výhod funkcí pro integraci například ikonu zobrazení na [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] úvodní obrazovky a o dialogové okno.

 Soubory Instalační služby systému Microsoft Windows jsou doporučeným způsobem, jak distribuovat vaše rozšíření VSPackages. Snadno použitelné balíčky Instalační služby systému Windows můžete spustit v libovolném operačním systému Windows nepodporuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Další informace najdete v tématu [Instalační služby systému Windows](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).

## <a name="in-this-section"></a>V tomto oddílu
- [Základní informace o Instalační službě systému Windows](../../extensibility/internals/windows-installer-basics.md)

 Poskytuje přehled Instalační služby systému Windows.

- [Scénáře instalace balíčku VSPackage](../../extensibility/internals/vspackage-setup-scenarios.md)

 Tento článek popisuje různé způsoby, které může podporovat-souběžnými instalacemi vaše rozšíření VSPackages a [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

- [Vytvoření balíčku Instalační služby systému Windows](../../extensibility/internals/authoring-a-windows-installer-package.md)

 Poskytuje přehled o obvyklé kroky instalační programy podle správně nainstalovat a integrovat do VSPackages [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

- [Zjištění požadavků na systém](../../extensibility/internals/detecting-system-requirements.md)

 Popisuje, jak můžete zjistit, instalační program [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a jeho součástmi a zrušit instalační program, pokud nejsou splněny požadavky na VSPackage.

- [Správa komponent](../../extensibility/internals/component-management.md)

 Popisuje, jak vyvíjet instalační program, který bude udržovat tak integritu předchozích verzích produktu.

- [Výběr instalačního adresáře pro balíček VSPackage](../../extensibility/internals/choosing-the-installation-directory-for-a-vspackage.md)

 Shrnuje možnosti pro vyhledání rozšíření VSPackages.

- [Registrace balíčku VSPackage](../../extensibility/internals/vspackage-registration.md)

 Popisuje, jak balíčky VSPackages zaregistrovaní v době instalace a proč samoregistračního není dobrý nápad.

- [Nasazování typů projektů](../../extensibility/internals/deploying-project-types.md)

 Popisuje, jak použít nový typ projektu agregátor pro typy projektů spravovaného kódu.

- [Postupy: Vygenerování informací registru pro instalační program](../../extensibility/internals/how-to-generate-registry-information-for-an-installer.md)

 Vysvětluje způsob používání RegPkg.exe ke generování manifestu registrace pro spravovaná VSPackage.

- [Příkazy, které se musí spustit po instalaci](../../extensibility/internals/commands-that-must-be-run-after-installation.md)

 Vysvětluje, jak spouštět příkazy po instalaci rozšíření VSPackages do integrace [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

- [Odinstalace balíčku VSPackage pomocí Instalační služby systému Windows](../../extensibility/internals/uninstalling-a-vspackage-with-windows-installer.md)

 Popisuje kroky, které instalační program musíte provést, když uživatelé odinstalaci vašeho balíčku VSPackage.