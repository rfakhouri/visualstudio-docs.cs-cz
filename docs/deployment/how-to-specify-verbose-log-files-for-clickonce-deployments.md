---
title: 'Postupy: Určení souborů podrobného protokolování pro nasazení ClickOnce | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- logs, ClickOnce deployment
- ClickOnce deployment, logging
ms.assetid: 0807a28d-2e40-4a51-ab10-308d808ded6b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ffc7fbdace660a894352623a3ff8765a165b5556
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56619495"
---
# <a name="how-to-specify-verbose-log-files-for-clickonce-deployments"></a>Postupy: Určení souborů podrobného protokolování pro nasazení ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] udržuje soubory protokolu aktivit pro všechna nasazení. Tyto protokoly dokumentu podrobnosti týkající se instalace, inicializace, aktualizaci a odinstalaci [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení. Pro zvýšení podrobností, která [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zápisy do těchto souborů protokolů pomocí Editoru registru (*regedit.exe*) Chcete-li určit úroveň podrobností.

> [!CAUTION]
>  Pokud Editor registru používán správně, můžete způsobit vážné problémy, které mohou vyžadovat přeinstalaci operačního systému. Pomocí Editoru registru na vlastní nebezpečí.

 Následující postup popisuje, jak zadat úroveň podrobností pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] soubory protokolu pro aktuálního uživatele. Pokud chcete snížit úroveň podrobností, odeberte tuto hodnotu registru.

### <a name="to-specify-verbose-log-files"></a>K určení souborů podrobného protokolování

1.  Otevřít *Regedit.exe*.

2.  Přejděte na uzel **HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment**.

3.  V případě potřeby vytvořte novou řetězcovou hodnotu s názvem `LogVerbosityLevel`.

4.  Nastavte `LogVerbosityLevel` hodnota, která se `1`.

## <a name="see-also"></a>Viz také:
- [Řešení potíží s nasazením ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)