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
ms.openlocfilehash: 29f6ab4b750370467fa75c2341e20264db756a7f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60077183"
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
- (Volitelné) Je-li zadán, vrátí možnost po zadaném počtu sekund bez vypnutí profileru a zavření souboru dat profilování.

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)