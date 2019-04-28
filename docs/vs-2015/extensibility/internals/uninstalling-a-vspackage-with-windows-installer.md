---
title: Odinstalace balíčku VSPackage pomocí Instalační služby systému Windows | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- packages, uninstalling
- VSPackages, uninstalling
- uninstalling VSPackages
ms.assetid: c4575ac7-82da-4af8-a375-ea756a101fbf
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6175b89db774598463d1f8ffaa03057ecb50a69b
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441180"
---
# <a name="uninstalling-a-vspackage-with-windows-installer"></a>Odinstalace balíčku VSPackage pomocí Instalační služby systému Windows
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ve většině případů instalační služby systému Windows můžete odinstalovat vašeho balíčku VSPackage pouze za "vrácení zpět" udělal pro instalaci vaší VSPackage. Vlastní akce popsané v [příkazy, musí být spustit po instalaci](../../extensibility/internals/commands-that-must-be-run-after-installation.md) po odinstalaci dojde také musí být spuštěn. Protože těsně před parametr InstallFinalize standardní akci pro instalaci a odinstalaci dojde k volání devenv.exe, položek tabulky CustomAction a InstallExecuteSequence sloužit obou případech.  
  
> [!NOTE]
> Spustit `devenv /setup` po odinstalaci balíčku MSI.  
  
 Obecně platí Pokud chcete přidat vlastní akce do balíčku Instalační služby systému Windows, je nutné zpracovat tyto akce během odinstalace a vrácení zpět. Pokud chcete přidat vlastní akce samoobslužné registrace vašeho balíčku VSPackage, například musíte přidat vlastní akce, příliš zrušit registraci.  
  
> [!NOTE]
> Je možné pro uživatele k instalaci vaší VSPackage a potom odinstalujte verze [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] se taky jsou integrované. Můžete zajistit, že vaše VSPackage odinstalace funguje v tomto scénáři odstraněním vlastní akce, které běží kód se závislostmi na [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="handling-launch-conditions-at-uninstall-time"></a>Zpracování podmínek pro spuštění v odinstalaci  
 Akce standard LaunchConditions načte řádky tabulky LaunchCondition zobrazit chyba zprávy, pokud nejsou splněny podmínky. Podle podmínek pro spuštění se obecně používají k zajištění, že jsou splněny požadavky na systém, obvykle můžete přeskočit podmínek pro spuštění během odinstalace přidáním podmínky, `NOT Installed`, řádek LaunchConditions LaunchCondition tabulky.  
  
 Další možností je přidat `OR Installed` spustit podmínky, které nejsou důležité při odinstalaci. Což zajišťuje, že podmínka bude vždy hodnotu true při odinstalaci a proto nebudou zobrazovat chybová zpráva stavu spuštění.  
  
> [!NOTE]
> `Installed` je vlastnost, kterou instalační služby systému Windows se nastaví, když zjistí, že vaše VSPackage je už nainstalovaná v systému.  
  
## <a name="see-also"></a>Viz také  
 [Windows Installer](http://msdn.microsoft.com/187d8965-c79d-4ecb-8689-10930fa8b3b5)   
 [Zjištění požadavků na systém](../../extensibility/internals/detecting-system-requirements.md)
