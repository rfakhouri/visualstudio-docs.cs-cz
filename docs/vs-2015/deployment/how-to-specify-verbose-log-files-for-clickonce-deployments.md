---
title: 'Postupy: Určení souborů podrobného protokolování pro nasazení ClickOnce | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- logs, ClickOnce deployment
- ClickOnce deployment, logging
ms.assetid: 0807a28d-2e40-4a51-ab10-308d808ded6b
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0efd71b38d3fcd8ae8241e31e721bd48e857d3bd
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54754171"
---
# <a name="how-to-specify-verbose-log-files-for-clickonce-deployments"></a>Postupy: Určení souborů podrobného protokolování pro nasazení ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] udržuje soubory protokolu aktivit pro všechna nasazení. Tyto protokoly dokumentu podrobnosti týkající se instalace, inicializace, aktualizaci a odinstalaci [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] nasazení. Pro zvýšení podrobností, která [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] zápisy do těchto souborů protokolů pomocí Editoru registru (**regedit.exe**) Chcete-li určit úroveň podrobností.  
  
> [!CAUTION]
>  Pokud Editor registru používán správně, můžete způsobit vážné problémy, které mohou vyžadovat přeinstalaci operačního systému. Pomocí Editoru registru na vlastní nebezpečí.  
  
 Následující postup popisuje, jak zadat úroveň podrobností pro [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] soubory protokolu pro aktuálního uživatele. Pokud chcete snížit úroveň podrobností, odeberte tuto hodnotu registru.  
  
### <a name="to-specify-verbose-log-files"></a>K určení souborů podrobného protokolování  
  
1.  Otevřít **Regedit.exe**.  
  
2.  Přejděte na uzel `HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment`.  
  
3.  V případě potřeby vytvořte novou řetězcovou hodnotu s názvem `LogVerbosityLevel`.  
  
4.  Nastavte `LogVerbosityLevel` hodnota, která se `1`.  
  
## <a name="see-also"></a>Viz také  
 [Řešení potíží s nasazením ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)
