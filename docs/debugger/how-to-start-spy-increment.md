---
title: 'Postupy: Spuštění nástroje Spy ++ | Dokumentace Microsoftu'
ms.date: 12/16/2018
ms.topic: conceptual
helpviewer_keywords:
- Spy++, starting
ms.assetid: 1d36813a-dc2a-4fda-9b3d-a38928a62ced
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91eda74b4f83f38434117ab1217d0a20d66d2842
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56712447"
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

2.  Enter **spyxx.exe**.

## <a name="see-also"></a>Viz také:
- [Použití nástroje Spy++](../debugger/using-spy-increment.md)
- [Zobrazení nástroje Spy++](../debugger/spy-increment-views.md)
- [Referenční dokumentace nástroje Spy++](../debugger/spy-increment-reference.md)