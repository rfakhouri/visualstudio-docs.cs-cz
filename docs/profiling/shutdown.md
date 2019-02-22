---
title: Vypnutí | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: deeb74e8e8763feb62b0cc21fcfbfbf3c6b220ca
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56596695"
---
# <a name="shutdown"></a>Vypnutí
**Vypnutí** možnost čeká všechny aktuálně profilovaný proces ukončit nebo odpojit, a pak profiler vypne a uzavře soubor dat profilování. **Vypnutí** možnost musí být poslední příkaz profilování.

 Pokud není zadán parametr časového limitu, **vypnutí** možnost čekat po neomezenou dobu. Pokud je zadán parametr časového limitu, vrátí se možnost po zadaném počtu sekund bez vypnutí profileru a zavření souboru dat.

 **Vypnutí** možnost musí být zadán v příkazovém řádku jedinou možností.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Shutdown[:Timeout]
```

#### <a name="parameters"></a>Parametry
 `Timeout`
 -   (Volitelné) Je-li zadán, vrátí možnost po zadaném počtu sekund bez vypnutí profileru a zavření souboru dat profilování.

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)