---
title: Stav | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ba656fa4-ef9d-4d8c-a3b6-739c3b5d23ae
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 25f452dcb473abf87d8992f36f5326973937e85e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967869"
---
# <a name="status"></a>Stav
*VSPerfCmd.exe* **stav** možnost zobrazí informace o stavu profileru a všechny procesy, které jsou právě profilována.

 **Stav** možnost musí být zadán v příkazovém řádku jedinou možností. Profiler je nutné inicializovat s *VSPerfCmd.exe* **Start** možnost před zobrazením libovolný stav.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Status
```

#### <a name="parameters"></a>Parametry
 Žádné

## <a name="remarks"></a>Poznámky
 **Stav** možnost se zobrazí následující informace o stavu pro profiler.

 **Název výstupního souboru** cestu a název souboru aktuálního souboru dat profilování.

 **Režim kolekce** UKÁZKOVÝ nebo trasování

 **Maximum procesů** maximální počet procesů, které jde Profilovat najednou a počet aktuálně aktivních procesů.

 **Maximální počet vláken** maximální počet vláken, které jde Profilovat najednou.

 **Počet vyrovnávacích pamětí** počet vyrovnávacích pamětí vyhrazený pro zápis dat profilování.

 **Velikost vyrovnávací paměti** velikost v bajtech vyrovnávací paměti.

 **Stav** možnost se zobrazí následující informace o stavu pro každý proces, který je právě profilována.

 **Proces** název profilovaný proces.

 **ID procesu** systémový identifikátor procesu.

 **Počet vláken** počtu vláken aktuálně spouští.

 **Počet operací Spustit/Zastavit** primární interní profiler počet řízení shromažďování dat pro tento proces. Počet musí být rovna jedné shromažďovat data. Počet operací spustit/zastavit lze ovládat pomocí rozhraní API profileru a možnosti, VSPerfCmd **GlobalOn**, **GlobalOff**, **ProcessOn**, **ProcessOff**, **ThreadOn**, a **ThreadOff**.

 **Počet operací Pozastavit/Pokračovat** sekundární interní profiler počet řízení shromažďování dat pro tento proces. Počet musí být menší než nebo rovna hodnotě nula, pokud chcete shromažďovat data. **Pozastavit/Pokračovat** počet může být používán pouze rozhraní API profileru.

 **Uživatelé s přístupovými oprávněními k monitoru** obsahuje seznam uživatelů, kteří mají přístup k profileru. Další uživatelé lze udělit přístup pomocí VSPerfCmd.exe **správce** možnost

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)