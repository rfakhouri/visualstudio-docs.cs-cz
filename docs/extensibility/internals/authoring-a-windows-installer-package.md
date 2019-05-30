---
title: Vytváření balíčku Instalační služby systému Windows | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .msi files, VSPackages
- msi files, VSPackages
ms.assetid: 0ce7c21d-0d3f-47fe-a0bb-eed506e32609
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: da68fa0a6c115a09ba2050f8c84ea6700ee4fc76
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315792"
---
# <a name="author-a-windows-installer-package"></a>Autor balíčku Instalační služby systému Windows
Datové jednotky modelu Instalační služby systému Windows. Místo psaní skriptu procedury kopírování souborů a zápis položky registru, například vytváříte řádků a sloupců do tabulek databáze, které obsahují data souborů a registru.

## <a name="database-entries"></a>Položky databáze
K instalaci VSPackage balíček Instalační služby systému Windows musí obsahovat položky databáze k provádění následujících úloh:

- Hledat systému k vyhledání verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] podporuje vašeho balíčku VSPackage (pomocí tabulek Instalační služby systému Windows, které zahrnují AppSearch CompLocator, RegLocator, DrLocator a podpis).

- Zrušit instalaci, pokud žádné podporovanou verzi [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je nainstalovaná, nebo pokud jiné požadavky na systém ze sady VSPackage není splněná (pomocí tabulky LaunchCondition).

- Instalace balíčku VSPackage a závislé soubory (pomocí adresáře, komponenty a soubor tabulky).

- Přidejte do registru (pomocí tabulky registru) odpovídajícími informacemi pro sady VSPackage.

- Integrace sady VSPackage v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] voláním **/Setup devenv.exe** (pomocí tabulky CustomAction).

Další informace najdete v tématu [Instalační služby systému Windows](/windows/desktop/Msi/windows-installer-portal).

## <a name="setup-tools"></a>Instalační program nástroje
Různé nástroje třetích stran instalace nabízejí vývojové prostředí pro balíčky Instalační služby systému Windows. Tyto bezplatné nástroje vám budou k dispozici:

- Program InstallShield limited edition

   Pomocí sady Visual Studio můžete získat omezenou verzi InstallShield **nový projekt** dialogového okna. Rozbalte **ostatní typy projektů** a pak vyberte **instalace a nasazení**. Vyberte šablonu InstallShield.

- Sada nástrojů XML Instalační služby systému Windows

   Sada nástrojů XML Instalační služby systému Windows (WiX) sestaví balíčky Instalační služby systému Windows ze zdrojových souborů XML. Sada nástrojů WiX je projekt open source Microsoftu. Stáhněte si zdrojový kód a spustitelné soubory z [sadu nástrojů Wix toolset](http://sourceforge.net/projects/wix).

   Pro komerční produkty, které se integrují do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] pomocí [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], naleznete v tématu [Visual Studio Marketplace](https://marketplace.visualstudio.com/).

## <a name="see-also"></a>Viz také:
- [Instalace balíčků VSPackage pomocí Instalační služby systému Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md)