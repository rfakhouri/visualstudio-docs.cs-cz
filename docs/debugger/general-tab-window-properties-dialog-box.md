---
title: Karta Obecné, dialogové okno Vlastnosti okna | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Window Properties dialog box, General Tab
ms.assetid: 19142c60-9b32-46ba-a556-b62fd77568c1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c5160c79e2c8dae474927e6af7ebdc9e371e9edc
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703224"
---
# <a name="general-tab-window-properties-dialog-box"></a>Karta Obecné, dialogové okno vlastnosti okna
Použití **Obecné** zobrazte informace o vybrané okno. Zobrazíte [dialogové okno Vlastnosti okna](../debugger/window-properties-dialog-box.md), přesuňte fokus [zobrazení Windows](../debugger/windows-view.md) okna. Vyberte jakékoli okno uzel ve stromu a pak zvolte **vlastnosti** z **zobrazení** nabídky.

 Následující nastavení jsou k dispozici na **Obecné** kartu:

|Položka|Popis|
|-----------|-----------------|
|**Titulek okna**|Text v záhlaví okna, nebo text obsažen v okně, pokud je ovládací prvek.|
|**Popisovač okna**|Jedinečné ID tohoto okna. Jsou opakovaně využívána popisovač okna; okno identifikují pouze po dobu platnosti tohoto okna.|
|**Proces okna**|Virtuální adresa funkce procedury okna pro toto okno. Toto pole také určuje, zda toto okno je okno Unicode, a určuje, zda je rozčleněných do podtříd.|
|**Obdélník**|Ohraničující obdélník okna. Zobrazí se také velikost pravoúhelníku. Jednotky jsou pixelů v souřadnicovém systému obrazovky.|
|**Obnovený Rect**|Ohraničující obdélník obnovené okna. Zobrazí se také velikost pravoúhelníku. Obnovený Rect budou lišit od obdélník pouze v případě, že je okno maximalizované ani minimalizováno. Jednotky jsou pixelů v souřadnicovém systému obrazovky.|
|**Rect klienta**|Ohraničující rámeček pro klientské oblasti okna. Zobrazí se také velikost pravoúhelníku. Jednotky jsou relativní k levé horní části klientské oblasti okna pixelů.|
|**Popisovač instance**|Popisovač instance aplikace. Instance popisovače nejsou jedinečné.|
|**ID ovládacího prvku nebo popisovač nabídky**|Pokud okno zobrazení je podřízené okno, zobrazí se ID ovládacího prvku popisku. ID ovládacího prvku je celé číslo, které identifikuje ID této podřízené okno ovládacího prvku. Pokud není okno se zobrazí podřízené okno, zobrazí se popisek nabídky zpracování. Popisovač nabídky je celé číslo, které identifikuje popisovač nabídky spojené s tímto oknem.|
|**Uživatelská Data**|Specifické pro aplikaci data, která je přiřazena tato struktura okna.|
|**Bajty okna**|Počet bajtů navíc spojený s tímto oknem. Význam těchto bajtů se určuje podle aplikace. Rozbalte položku seznamu zobrazíte bajtové hodnoty ve formátu DWORD.|