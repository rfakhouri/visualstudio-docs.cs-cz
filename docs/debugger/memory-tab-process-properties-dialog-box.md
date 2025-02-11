---
title: Karta paměť, dialogové okno vlastností procesu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: a70785f2-5997-40ec-a90f-80a52449768b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6bdfc2740094c807818922f09ca3fef0a21c9e1a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62931282"
---
# <a name="memory-tab-process-properties-dialog-box"></a>Karta Paměť, dialogové okno vlastností procesu
Použití **paměti** zobrazte použití paměti v procesu. Pro zobrazení [dialogové okno vlastností procesu](../debugger/process-properties-dialog-box.md), přesunout fokus [zobrazení procesů](../debugger/processes-view.md) okno. Vyberte libovolný uzel procesu ve stromové struktuře a pak zvolte **vlastnosti** z **zobrazení** nabídky.

 Následující nastavení jsou k dispozici na **paměti** kartu:

|Entry|Popis|
|-----------|-----------------|
|**Virtuální bajty**|Aktuální velikost (v bajtech) prostoru virtuálních adres je využívána procesem. Použití virtuálního adresového prostoru ještě nutně neznamená odpovídající použití buď disku nebo stránek hlavní paměti. Však virtuální prostor je však konečný a pomocí příliš mnoho může omezit schopnost procesu načítat knihovny.|
|**Virtuální bajty – Špička**|Maximální počet bajtů virtuálního adresového prostoru procesu využil v jednom okamžiku.|
|**Pracovní sada**|Sada stránek paměti nedávno přistupovala vlákna daného procesu. Pokud volné paměti v počítači je nad prahovou hodnotou, ponechají se stránky v pracovní sadě procesu, i když nejsou v použití. Když volná paměť počítače klesne pod prahovou hodnotu, jsou oříznut stránky z pracovní sady. Pokud jsou potřeba, bude se softwarovou chybou zpátky do pracovní sady před opuštěním hlavní paměti.|
|**Nejvyšší hodnota pracovní sady**|Maximální počet stránek v pracovní sadě procesu v libovolném bodě v čase.|
|**Bajty stránkovaného fondu**|Aktuální velikost stránkovaného fondu, která byla přidělena procesu. Stránkovaný fond je na oblast paměti systému, kde získat součásti operačního systému místo podle jejich provádět úkoly určené. Stránky stránkovaného fondu může být stránkování na stránkovacího souboru není přístup k systému zachovaného časová období.|
|**Bajty nestránkovaného fondu**|Aktuální počet bajtů v nestránkovaného fondu přidělené procesem. Nestránkovaného fondu je na oblast paměti systému, kde místa se získávají pomocí součásti operačního systému podle jejich provádět úkoly určené. Stránky nestránkovaného fondu nemůže být stránkování na stránkovacího souboru; zůstanou hlavní paměti tak dlouho, dokud jejich přidělení.|
|**Nesdílené bajty**|Aktuální počet bytů, které tento proces alokoval, které nelze sdílet s jinými procesy.|
|**Volné bajty**|Celkový počet nevyužitých virtuálního adresového prostoru tohoto procesu.|
|**Vyhrazené bajty**|Celková velikost virtuální paměti vyhrazená pro budoucí použití tímto procesem.|
|**Volné bajty bitové kopie**|Velikost virtuálního adresového prostoru, který se nepoužívá nebo vyhrazený pro obrázky v rámci tohoto procesu.|
|**Vyhrazené bajty bitové kopie**|Součet všech virtuální paměti vyhrazená imagí spuštění v rámci tohoto procesu.|