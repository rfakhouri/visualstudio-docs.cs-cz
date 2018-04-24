---
title: 'Postupy: nastavení možností názvu datového souboru výkonu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: d7a8d6b9-ab23-46fb-98ed-774781157860
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0687b4f56906aeca0866f8d5d6ad7d329bb84df6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-set-performance-data-file-name-options"></a>Postupy: nastavení možností názvu datového souboru výkonu

Ve výchozím nastavení uložte soubor profilování dat (.vsp) pomocí následující syntaxe:

*Path\VSP-File\YYMMDD(N)* **.vsp**

Pro relaci, výkon, můžete změnit libovolný pojmenování parametr na stránce Obecné v dialogovém okně Vlastnosti.

|||
|-|-|
|*Cesta*|Adresář, který obsahuje sestavu. Výchozí umístění je složka řešení nebo výchozí umístění pro projekty a řešení pro uživatele.|
|*VSP – soubor*|Název datového souboru profilování. Výchozí název je název řešení nebo spustitelného souboru, je profilovaným.|
|*RRMMDD*|Razítka data, který ukazuje rok, měsíc a den, která nebyla shromážděna profilování data.|
|*(NE)*|Pokud existuje více než jeden profilování datový soubor, zvýšena číslo se přidá k názvu souboru mezi závorky.|

## <a name="to-change-the-naming-syntax-of-the-profiling-data-files-of-a-performance-session"></a>Chcete-li změnit pojmenování syntaxe datových souborů profilace výkonnostní relace

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na název výkonnostní relace a pak klikněte na tlačítko **vlastnosti**.

2. Klikněte na tlačítko **Obecné**.

3. V části **sestavy**, změnit následující nastavení:

    |||
    |-|-|
    |**Umístění sestavy**|Zadejte adresář pro ukládání datových souborů profilování.|
    |**Název sestavy**|Zadejte základní název pro soubory.|
    |**Automaticky přidat nové sestavy do relace**|Zaškrtněte políčko automaticky přidat do relace výkon datového souboru.|
    |**Připojit narůstajícími číslo generované sestav**|Zaškrtněte políčko Přidat narůstajícími číslo k názvu souboru, pokud existuje více než jeden soubor se stejným názvem. Zrušte zaškrtnutí políčka Přepsat existující soubor.|
    |**Používat časové razítko pro číslo**|Zaškrtněte políčko Přidat datestamp k názvu souboru.|