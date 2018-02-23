---
title: "Postupy: Zadejte příkazy před a po instrumentaci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.instrument
helpviewer_keywords:
- profiling tools, pre-instrument events
- events [Visual Studio], pre-instrument
- pre-instrument events, performance tools
ms.assetid: 6a8d5340-1d1b-4d81-88dd-8e1f435eb828
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 641b03b0740cc05275135753eb525fde271239e9
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2018
---
# <a name="how-to-specify-pre--and-post-instrument-commands"></a>Postupy: Určení příkazů k provedení před instrumentací a po instrumentaci

Můžete zadat příkazy, které před nebo po jsou vybaveny binárních souborů v relaci výkonu. Všemi příkazy, které můžou být vystavené z příkazového řádku lze zadat jako před instrumentací nebo po instrumentaci událost. Můžete například zadat příkazy, které automatizují opětovného podpisu sestavení se silným názvem klíčem v dávkovém souboru, která se spustí po jsou vybaveny binární soubory.

Můžete zadat příkazy pro všechny instrumentované binární soubory v profilaci spustit nebo jednotlivých binárních souborů. Můžete však zadat jenom jeden příkaz před instrumentací na spuštění před a spustit po dokončení procesu instrumentace jenom jeden příkaz po instrumentaci. Nelze zadat příkazy pro obě všechny binární soubory a jednotlivých binárních souborů. Když zadáte příkazy pro všechny binární soubory, příkazy se spouštějí před nebo po každé binární instrumentace v relaci.

Pracovní adresář, ve kterém jsou prováděny příkazy závisí na operační systen, ve kterém je spuštěn [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] a na cílové platformy PROFILOVANÉHO aplikace.

 **32bitové počítače**

Na 32bitové počítače je výchozí adresář profiler nástrojů 10.0\Team disk\Program Files\Microsoft Visual Studio Tools nástroje.

**64bitové počítače**

Na 64bitových počítačích zadejte cestu podle cílové platformy PROFILOVANÉHO aplikace:

- Pro 32bitové aplikace je výchozí adresář profiler nástrojů:

     *Jednotka*\Program soubory (x86) \Microsoft Visual Studio 10.0\Team nástroje nástroje

- Pro 64bitové aplikace je výchozí adresář profiler nástrojů:

     *Drive*\Program Files (x86)\Microsoft Visual Studio 10.0\Team Tools\Performance Tools\x64

## <a name="to-specify-pre-instrument-commands"></a>Chcete-li určit příkazy před instrumentací

1. Proveďte jeden z následujících kroků:

    - Příkazy před instrumentací pro všechny binární soubory v relaci výkonu, vyberte uzel relace výkonu v **prohlížeč výkonu**a potom klikněte pravým tlačítkem a vyberte **vlastnosti**.

    - Pokud chcete zadat příkazy před instrumentací pro konkrétní binární, klikněte pravým tlačítkem na název binárního souboru v **cíle** seznam výkonnostní relace a potom vyberte **vlastnosti**.

2. V **stránky vlastností**, klikněte na tlačítko **instrumentace**.

3. Zadejte příkaz v **příkazového řádku** textového pole pod **události před Instrumentací**.

    > [!NOTE]
    > Kliknutí tlačítko se třemi tečkami **(...)**  se přiléhající k **příkazového řádku** pole Procházet a vyberte příslušný soubor .exe, CMD nebo BAT.

4. Click **OK**.

     Zakázat příkaz spouštění bez nutnosti ho odebrat, vyberte **vyloučit z instrumentace** zaškrtávací políčko. Ke změně kompilátoru nebo linkeru nastavení můžete použijte na stránkách vlastností projektu.

## <a name="to-specify-post-instrument-commands"></a>Chcete-li určit příkazy po instrumentaci

1. Proveďte jeden z následujících kroků:

    - Po instrumentaci příkazy pro všechny binární soubory v relaci výkonu, vyberte uzel relace výkonu v **prohlížeč výkonu**a potom klikněte pravým tlačítkem a vyberte **vlastnosti**.

    - Pokud chcete zadat příkazy po instrumentaci pro konkrétní binární, klikněte pravým tlačítkem na název binárního souboru v **cíle** seznam výkonnostní relace a potom vyberte **vlastnosti**.

2. V **stránky vlastností**, klikněte na tlačítko **instrumentace**.

3. Zadejte příkaz v **příkazového řádku** textového pole pod **po instrumentovat svoje události**.

    > [!NOTE]
    > Kliknutí tlačítko se třemi tečkami **(...)**  se přiléhající k **příkazového řádku** pole Procházet a vyberte příslušný soubor .exe, CMD nebo BAT.

4. Click **OK**.

     Zakázat příkaz spouštění bez nutnosti ho odebrat, vyberte **vyloučit z instrumentace** zaškrtávací políčko. Ke změně kompilátoru nebo linkeru nastavení můžete použijte na stránkách vlastností projektu.

## <a name="see-also"></a>Viz také

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)