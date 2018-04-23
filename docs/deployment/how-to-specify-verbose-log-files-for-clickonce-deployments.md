---
title: 'Postupy: určení souborů podrobného protokolování pro nasazení ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8153625ec875cb54b0fc7b626d0cef61df2e9b71
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-specify-verbose-log-files-for-clickonce-deployments"></a>Postupy: Určení souborů podrobného protokolování pro nasazení ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] udržuje aktivity soubory protokolu pro všechna nasazení. Tyto protokoly dokumentu podrobnosti vztahující se k instalaci, inicializaci, aktualizaci a odinstalaci [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení. Pro zvýšení podrobností, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zápisy na tyto soubory protokolu pomocí Editoru registru (**regedit.exe**) k určení úrovně podrobností.  
  
> [!CAUTION]
>  Pokud Editor registru používán správně, může způsobit vážné problémy, které mohou vyžadovat přeinstalaci operačního systému. Pomocí Editoru registru na vlastní nebezpečí.  
  
 Následující postup popisuje, jak určit úroveň podrobností pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] soubory protokolu pro aktuálního uživatele. Chcete-li snížit úroveň podrobností, odeberte tuto hodnotu registru.  
  
### <a name="to-specify-verbose-log-files"></a>K určení souborů podrobného protokolování  
  
1.  Otevřete **Regedit.exe**.  
  
2.  Přejděte na uzel `HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment`.  
  
3.  V případě potřeby vytvořte novou řetězcovou hodnotu s názvem `LogVerbosityLevel`.  
  
4.  Nastavte `LogVerbosityLevel` hodnotu `1`.  
  
## <a name="see-also"></a>Viz také  
 [Řešení potíží s nasazením ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)