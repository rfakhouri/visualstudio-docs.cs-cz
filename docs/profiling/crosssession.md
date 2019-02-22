---
title: CrossSession | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b9fcb9c3-7903-478c-9b7c-dbd94092fcba
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8087f620f457f1e88ee6dc9ffff90f5c8747e50d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56626827"
---
# <a name="crosssession"></a>CrossSession
*VSPerfCmd.exe* **CrossSession** možnost umožňuje profileru začnete shromažďovat data z všechny relace konzoly. **CrossSession** možnost musí být použita s **Start** možnost.

 Můžete použít zkratku **CS** místo **CrossSession**.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Start:Method /CrossSession [Options]
```

#### <a name="parameters"></a>Parametry
 Žádná

## <a name="valid-options"></a>Platné možnosti
 Chcete-li povolit profilaci v jiné relaci **CrossSession** možnost musí být zadaný pomocí **Start** možnost. **CrossSession** musí být zadaná také v jakémkoli následné **připojit nástroj VSPerfCmd** a **odpojit** příkazy.

 **Spusťte:** `Method` **Start** možnost inicializuje profiler k zadané metodě profilování.

 **Připojení:** _Identifikátor PID_[**,**_PID_] Begins profilace konkrétních procesů.

 **Odpojit**[**:**_PID_[,_PID_]] zastaví profilaci konkrétních procesů.

## <a name="example"></a>Příklad
 V tomto příkladu **CrossSession** možnost se používá k připojení k aplikaci, která byla spuštěna v jiné relaci konzoly.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /CrossSession
VSPerfCmd.exe /Attach:12345 /CS
```

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)