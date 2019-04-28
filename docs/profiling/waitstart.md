---
title: WaitStart | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6307dcad45b7e2c8164aa892c4598d577e4ea464
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62998963"
---
# <a name="waitstart"></a>WaitStart
Možnost příčiny WaitStart *VSPerfCmd.exe* Start dílčí příkaz, který vrátí pouze v případě, že profiler byl inicializován nebo po uplynutí zadaném počtu sekund. Ve výchozím nastavení, Start příkaz vrátí hodnotu okamžitě. Vrátí dílčí příkaz Start bez inicializace okna profilování, vrátí se chyba. Pokud není zadaný počet sekund, po neomezenou dobu čeká příkazu Start.

 WaitStart možnost je užitečná v dávkových souborech a zajistit, že profiler byl inicializován.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]
```

#### <a name="parameters"></a>Parametry
 `Seconds` Počet sekund čekání před návratem z dílčích příkazu Start.

## <a name="required-options"></a>Požadované možnosti
 Možnost WaitStart jde použít jenom s dílčího příkazu Start.

 **Výstup:** `filename` Určuje název výstupního souboru.

## <a name="remarks"></a>Poznámky

## <a name="example"></a>Příklad
 V tomto příkladu soubor batch příkazu Start. Počkejte 5 sekund kvůli na inicializaci profileru.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5
if not %errorlevel% 0 goto :error_tag
VSPerfCmd.exe /Launch:TestApp.exe
goto :end
:error_tag
@echo Could not start Profiler!
@echo Error %errorlevel%
:end
```