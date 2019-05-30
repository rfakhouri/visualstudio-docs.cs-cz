---
title: Odinstalace balíčku VSPackage pomocí Instalační služby systému Windows | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- packages, uninstalling
- VSPackages, uninstalling
- uninstalling VSPackages
ms.assetid: c4575ac7-82da-4af8-a375-ea756a101fbf
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4ddb09668d3114c055ddac1e4fb677a46754f388
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66344763"
---
# <a name="uninstalling-a-vspackage-with-windows-installer"></a>Odinstalace balíčku VSPackage pomocí Instalační služby systému Windows
Ve většině případů instalační služby systému Windows můžete odinstalovat vašeho balíčku VSPackage pouze za "vrácení zpět" udělal pro instalaci vaší VSPackage. Vlastní akce popsané v [příkazy, musí být spustit po instalaci](../../extensibility/internals/commands-that-must-be-run-after-installation.md) po odinstalaci dojde také musí být spuštěn. Protože těsně před parametr InstallFinalize standardní akci pro instalaci a odinstalaci dojde k volání devenv.exe, položek tabulky CustomAction a InstallExecuteSequence sloužit obou případech.

> [!NOTE]
> Spustit `devenv /setup` po odinstalaci balíčku MSI.

 Obecně platí Pokud chcete přidat vlastní akce do balíčku Instalační služby systému Windows, je nutné zpracovat tyto akce během odinstalace a vrácení zpět. Pokud chcete přidat vlastní akce samoobslužné registrace vašeho balíčku VSPackage, například musíte přidat vlastní akce, příliš zrušit registraci.

> [!NOTE]
> Je možné pro uživatele k instalaci vaší VSPackage a potom odinstalujte verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] se taky jsou integrované. Můžete zajistit, že vaše VSPackage odinstalace funguje v tomto scénáři odstraněním vlastní akce, které běží kód se závislostmi na [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="handling-launch-conditions-at-uninstall-time"></a>Zpracování podmínek pro spuštění v odinstalaci
 Akce standard LaunchConditions načte řádky tabulky LaunchCondition zobrazit chyba zprávy, pokud nejsou splněny podmínky. Podle podmínek pro spuštění se obecně používají k zajištění, že jsou splněny požadavky na systém, obvykle můžete přeskočit podmínek pro spuštění během odinstalace přidáním podmínky, `NOT Installed`, řádek LaunchConditions LaunchCondition tabulky.

 Další možností je přidat `OR Installed` spustit podmínky, které nejsou důležité při odinstalaci. Což zajišťuje, že podmínka bude vždy hodnotu true při odinstalaci a proto nebudou zobrazovat chybová zpráva stavu spuštění.

> [!NOTE]
> `Installed` je vlastnost, kterou instalační služby systému Windows se nastaví, když zjistí, že vaše VSPackage je už nainstalovaná v systému.

## <a name="see-also"></a>Viz také
- [Windows Installer](https://msdn.microsoft.com/library/187d8965-c79d-4ecb-8689-10930fa8b3b5)
- [Zjištění požadavků na systém](../../extensibility/internals/detecting-system-requirements.md)