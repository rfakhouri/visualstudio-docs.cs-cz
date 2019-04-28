---
title: 'Postupy: Nastavení možností názvu datového souboru výkonu | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d7a8d6b9-ab23-46fb-98ed-774781157860
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2b83b0aa083ca115797c9dc1cd8345d397307177
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62539266"
---
# <a name="how-to-set-performance-data-file-name-options"></a>Postupy: Nastavení možností názvu datového souboru výkonu

Ve výchozím nastavení, uložte dat profilování (. *Vsp*) souborů pomocí následující syntaxe:

*Path\VSP-File\YYMMDD(N)* **.vsp**

Žádné pojmenování parametru můžete změnit na **Obecné** stránky dialogové okno Vlastnosti relace výkonu.

|||
|-|-|
|*Cesta*|Adresář, který obsahuje sestavu. Výchozí umístění je složka řešení nebo výchozí umístění pro projekty a řešení pro daného uživatele.|
|*VSP-File*|Název souboru dat profilování. Výchozí název je název řešení nebo spustitelného souboru, která je profilována.|
|*YYMMDD*|Časové razítko, který ukazuje, rok, měsíc a den, shromážděná data profilace.|
|*(N)*|Pokud existuje více než jeden soubor dat profilování se zvyšující číslo přidá k názvu souboru mezi závorky.|

## <a name="to-change-the-naming-syntax-of-the-profiling-data-files-of-a-performance-session"></a>Chcete-li změnit pojmenování syntaxe datových souborů profilace relace výkonu

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a potom klikněte na **vlastnosti**.

2. Klikněte na tlačítko **Obecné**.

3. V části **sestavy**, změnit následující nastavení:

    |||
    |-|-|
    |**Umístění sestavy**|Zadejte adresář pro uložení souborů dat profilování.|
    |**Název sestavy**|Zadejte základní název pro soubory.|
    |**Automaticky přidávat nové zprávy do relace**|Zaškrtněte políčko k automatickému přidávání datového souboru do relace výkonu.|
    |**Přidat zvětšující se číslo do vygenerovaných sestav**|Zaškrtněte políčko Přidat zvětšující se číslo k názvu souboru, pokud existuje více než jeden soubor se stejným názvem. Zrušte zaškrtnutí políčka pro přepis existujícího souboru.|
    |**Použít časové razítko pro číslo**|Zaškrtněte políčko pro přidání datestamp k názvu souboru.|