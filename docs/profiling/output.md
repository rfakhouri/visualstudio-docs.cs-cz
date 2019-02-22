---
title: Výstup | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 78d5b39908bc0ffa39533c22ea4effcbe97397b7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56613801"
---
# <a name="output"></a>Výstup
**Výstup** Určuje název souboru dat profilování pro relaci výkonu. **Výstup** musí být použit s **Start** možnost.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Start:Method /Output:FileName [Options]
```

#### <a name="parameters"></a>Parametry
 `FileName` Název datového souboru. Jsou přijímány úplné a částečné cesty. Pokud cesta není zadaná, soubor se vytvoří v aktuálním adresáři.

## <a name="required-options"></a>Požadované možnosti
 **Výstup** možnost musí být použita s **Start** možnost.

 **Spusťte:** `Method` Určuje název výstupního souboru.

## <a name="example"></a>Příklad
 V následujícím příkladu je vytvořen soubor dat profilování v aktuálním adresáři.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
```

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)