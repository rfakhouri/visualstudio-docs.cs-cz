---
title: Args | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 20c35949-1f29-4282-ac75-4e6c237d71bc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 036b13a7fea5d64e23e2b7d5ccbd8a7b17f91176
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56608510"
---
# <a name="args"></a>Args
VSPerfCmd.exe **Args** určuje seznam argumentů, které se předají k cílové aplikaci z **spuštění** podpříkaz.

 **Args** jde použít jenom při **spuštění** je také zadán v příkazovém řádku. **Args** je volitelný při **spuštění** určena.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Launch:AppName /Args:Arguments [Options]
```

#### <a name="parameters"></a>Parametry
 `Arguments` Seznam argumentů k cílové aplikaci z **spuštění** příkazu.

## <a name="required-options"></a>Požadované možnosti
 **Spuštění:** `AppName` Zadaná aplikace spustí a začne profilace pomocí metody odběru vzorků.

## <a name="example"></a>Příklad
 V následujícím příkladu **Args** možnost předat argumenty do TestApp.exe.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
VSPerfCmd.exe /Launch:TestApp.exe /Args:"123, 'Hello World'"
```

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Profilace webových aplikací ASP.NET.](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profilace služeb](../profiling/command-line-profiling-of-services.md)