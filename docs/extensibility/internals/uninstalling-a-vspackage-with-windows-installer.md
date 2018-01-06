---
title: "Odinstalace VSPackage pomocí Instalační služby systému Windows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- packages, uninstalling
- VSPackages, uninstalling
- uninstalling VSPackages
ms.assetid: c4575ac7-82da-4af8-a375-ea756a101fbf
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ee8ad89e02dfa8aebbb39a9d7ebe523ad01bb7e9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="uninstalling-a-vspackage-with-windows-installer"></a>Odinstalace VSPackage pomocí Instalační služby systému Windows
Ve většině případů instalační služby systému Windows můžete odinstalovat vaší VSPackage právě pomocí "vrácení zpět" co se k instalaci vaší VSPackage. Vlastní akce popsané v [příkazy, musí být spustit po instalaci](../../extensibility/internals/commands-that-must-be-run-after-installation.md) po odinstalaci také musí být spuštěn. Protože těsně před parametr InstallFinalize standardní akci pro instalaci a odinstalaci dojde k volání devenv.exe, položek tabulky CustomAction a InstallExecuteSequence sloužit obou případech.  
  
> [!NOTE]
>  Spustit `devenv /setup` po odinstalování balíčku MSI.  
  
 Obecně platí Pokud přidáte vlastní akce do balíčku Instalační služby systému Windows, je nutné zpracovat tyto akce během odinstalace a vrácení zpět. Pokud přidáte vlastní akce registruje vaší VSPackage, například musíte přidat vlastní akce se zrušit registraci, příliš.  
  
> [!NOTE]
>  Je možné pro uživatele k instalaci vaší VSPackage a pak odinstalaci verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] s taky jsou integrované. Vám může pomoci zajistit, že vaše VSPackage odinstalace funguje v tomto scénáři odstraněním vlastní akce, které spustit kód s závislosti na [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="handling-launch-conditions-at-uninstall-time"></a>Podmínky spuštění zpracování na odinstalovat čas  
 Standardní akcí LaunchConditions čte řádky z tabulky LaunchCondition zobrazit chyba zpráv, pokud nejsou splněné podmínky. Podmínky spuštění se obecně používají pro jistotu, že jsou splněny požadavky na systém, obvykle můžete přeskočit podmínky spuštění během odinstalace přidáním podmínku `NOT Installed`, řádek LaunchConditions LaunchCondition tabulky.  
  
 Alternativou je přidat `OR Installed` spustíte podmínky, které nejsou důležité během odinstalace. Který zajišťuje, že podmínka bude vždy hodnotu true při odinstalaci a proto nebude zobrazí chybová zpráva podmínka spuštění.  
  
> [!NOTE]
>  `Installed`je vlastnost, kterou instalační služby systému Windows se nastavuje, když zjistí, zda vaše VSPackage již je nainstalovaná v systému.  
  
## <a name="see-also"></a>Viz také  
 [Instalační služba systému Windows](http://msdn.microsoft.com/en-us/187d8965-c79d-4ecb-8689-10930fa8b3b5)   
 [Zjištění požadavků na systém](../../extensibility/internals/detecting-system-requirements.md)