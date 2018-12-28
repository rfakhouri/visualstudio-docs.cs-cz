---
title: 'Postupy: Spuštění nástroje Spy ++ | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 12/16/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Spy++, starting
ms.assetid: 1d36813a-dc2a-4fda-9b3d-a38928a62ced
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5143c34f0c344fecec82a5d08b2e7fb9b95ac1bc
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53646864"
---
# <a name="how-to-start-spy"></a>Postupy: Spuštění nástroje Spy++

Můžete spustit nástroje Spy ++ ze sady Visual Studio nebo příkazového řádku.  
  
 Při spuštění nástroje Spy ++, pokud se zobrazí zpráva požádat oprávnění k provádění změn do počítače, vyberte **Ano**.  
  
> [!NOTE]
>  Můžete spustit pouze jedna instance nástroje Spy ++. Pokud se pokusíte spustit druhé instance, způsobí pouze aktuálně spuštěnou instanci získat fokus.

## <a name="prerequisites"></a>Požadavky

Spy ++ vyžaduje následující součásti. Tyto součásti můžete vybrat z instalačního programu sady Visual Studio tak, že vyberete **jednotlivé komponenty** kartu a pak vyberete následující součásti.

* V části ladění a testování, vyberte **nástroje pro profilaci v C++**
* V části vývojových aktivit, vyberte **Visual Studio C++ – základní funkce**

Pokud jste provedli změny, postupujte podle pokynů k instalaci těchto součástí.
  
## <a name="start-spy-from-visual-studio"></a>Spuštění nástroje Spy ++ ze sady Visual Studio
  
Na **nástroje** nabídce vyberte možnost **nástroje Spy ++**.  
  
Protože nástroje Spy ++ běží nezávisle na sobě po spuštění sady Visual Studio můžete zavřít.  
  
> [!NOTE]
>  Při protokolování zpráv pomocí nástroje Spy ++, může to způsobit pomalejší operačního systému.  
  
## <a name="start-spy-at-a-command-prompt"></a>Spuštění nástroje Spy ++ z příkazového řádku  
  
1.  V okně příkazového řádku přejděte do složky, která obsahuje spyxx.exe. Obvykle je cesta k této složce... \\ *Instalační složky sady visual Studio*\Common7\Tools\\.  
  
2.  Zadejte **spyxx.exe**. 
  
## <a name="see-also"></a>Viz také:  
 [Použití nástroje Spy ++](../debugger/using-spy-increment.md)   
 [Zobrazení nástroje Spy ++](../debugger/spy-increment-views.md)   
 [Referenční dokumentace nástroje Spy++](../debugger/spy-increment-reference.md)