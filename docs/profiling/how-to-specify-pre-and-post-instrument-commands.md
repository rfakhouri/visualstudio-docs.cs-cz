---
title: 'Postupy: Určení příkazů k provedení před instrumentací a po instrumentaci | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.instrument
helpviewer_keywords:
- profiling tools, pre-instrument events
- events [Visual Studio], pre-instrument
- pre-instrument events, performance tools
ms.assetid: 6a8d5340-1d1b-4d81-88dd-8e1f435eb828
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d0471d51ef00e176ab379a79a141ffd49c23aa28
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54923698"
---
# <a name="how-to-specify-pre--and-post-instrument-commands"></a>Postupy: Určení příkazů k provedení před instrumentací a po instrumentaci

Můžete zadat příkazy, které spustit před nebo po jsou instrumentované binární soubory v relaci výkonu. Jakýkoli příkaz, který může být vydán z příkazového řádku můžete zadat jako před instrumentací nebo události po instrumentaci. Například můžete zadat příkazy, které automatizují opětovného podepsání sestavení silným názvem klíčem v dávkovém souboru, který se spouští po binární soubory jsou instrumentovány.

Můžete zadat příkazy pro instrumentované binární soubory při spuštění profilování nebo jednotlivých binárních souborů. Můžete však zadat jenom jeden příkaz před instrumentací prováděný a pouze jeden příkaz po instrumentaci spustit po dokončení procesu instrumentace. Nelze zadat příkazy pro obě všechny binární soubory a jednotlivých binárních souborů. Při zadávání příkazů pro všechny binární soubory jsou spouštěny příkazy před nebo po instrumentaci každého binárního souboru v relaci.

Pracovní adresář, ve kterém jsou spouštěny příkazy závisí na operačním systému, kde je spuštěn nástroj [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] a na cílové platformě profilované aplikace.

Chcete-li získat cestu k nástrojů pro profilaci, naleznete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).

## <a name="to-specify-pre-instrument-commands"></a>Chcete-li určit příkazy před instrumentací

1. Proveďte jeden z následujících kroků:

    - Pokud chcete zadat příkazy před instrumentací pro všechny binární soubory do relace výkonu, vyberte uzel relace výkonu v **prohlížeč výkonu**a pak klikněte pravým tlačítkem a vyberte **vlastnosti**.

    - Pokud chcete zadat příkazy před instrumentací pro konkrétní binární soubor, klikněte pravým tlačítkem na název binárního souboru v **cíle** seznam výkonnostní relaci a pak vyberte **vlastnosti**.

2. V **stránky vlastností**, klikněte na tlačítko **instrumentace**.

3. Zadejte příkaz v **příkazového řádku** textového pole pod **události před Instrumentací**.

    > [!NOTE]
    > Můžete kliknout na tlačítko se třemi tečkami **(...)**  , který je vedle **příkazového řádku** pole vyhledejte a vyberte příslušný soubor .exe, .cmd nebo. bat.

4. Klikněte na **OK**.

     Chcete-li zakázat spouštění příkazu ale neodebrali, vyberte **vyloučit z instrumentace** zaškrtávací políčko. Pokud chcete upravit kompilátoru nebo linkeru, nastavení, použijte stránky vlastností projektu.

## <a name="to-specify-post-instrument-commands"></a>Chcete-li určit příkazy po instrumentaci

1. Proveďte jeden z následujících kroků:

    - Pokud chcete zadat příkazy po instrumentaci pro všechny binární soubory do relace výkonu, vyberte uzel relace výkonu v **prohlížeč výkonu**a pak klikněte pravým tlačítkem a vyberte **vlastnosti**.

    - Pokud chcete zadat příkazy po instrumentaci pro konkrétní binární soubor, klikněte pravým tlačítkem na název binárního souboru v **cíle** seznam výkonnostní relaci a pak vyberte **vlastnosti**.

2. V **stránky vlastností**, klikněte na tlačítko **instrumentace**.

3. Zadejte příkaz v **příkazového řádku** textového pole pod **události po instrumentaci**.

    > [!NOTE]
    > Můžete kliknout na tlačítko se třemi tečkami **(...)**  , který je vedle **příkazového řádku** pole vyhledejte a vyberte příslušný soubor .exe, .cmd nebo. bat.

4. Klikněte na **OK**.

     Chcete-li zakázat spouštění příkazu ale neodebrali, vyberte **vyloučit z instrumentace** zaškrtávací políčko. Pokud chcete upravit kompilátoru nebo linkeru, nastavení, použijte stránky vlastností projektu.

## <a name="see-also"></a>Viz také:

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)
