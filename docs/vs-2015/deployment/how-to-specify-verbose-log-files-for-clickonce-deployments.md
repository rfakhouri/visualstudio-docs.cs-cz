---
title: 'Postupy: určení souborů podrobného protokolování pro nasazení ClickOnce | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
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
manager: wpickett
ms.openlocfilehash: b30260267fca5b7de16316e84082fc3b464f7deb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668821"
---
# <a name="how-to-specify-verbose-log-files-for-clickonce-deployments"></a>Postupy: Určení souborů podrobného protokolování pro nasazení ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: určení podrobné soubory protokolů pro nasazení ClickOnce](https://docs.microsoft.com/visualstudio/deployment/how-to-specify-verbose-log-files-for-clickonce-deployments).  
  
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



