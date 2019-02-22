---
title: Konzoly | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e825ba66-1383-46ad-8712-396bc9c14036
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 74a5cecbdf3bba942c888a5cde3d49236047f4ee
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607873"
---
# <a name="console"></a>Konzola
VSPerfCmd.exe **konzoly** možnost spustí aplikaci, která zadané v novém okně příkazového řádku. **Konzola** jde použít jenom s příkazu vsperfcmd proveďte **spuštění** možnost. Pokud aplikace není aplikace pomocí příkazového řádku **konzoly** nemá žádný vliv.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Launch:AppName /Console
```

#### <a name="parameters"></a>Parametry
 Žádná

## <a name="required-options"></a>Požadované možnosti
 **Konzola** lze zadat pouze na příkazovém řádku, který také obsahuje **spuštění** možnost.

 **Spuštění:** `AppName` Spuštění profileru a aplikace určené `AppName`.

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)