---
title: Karta třída, dialogové okno Vlastnosti okna | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Window Properties dialog box, Class Tab
ms.assetid: eaec9f07-d580-436d-934d-76c4e59439aa
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0917c9a038b42e6302ec1f1782f095ca397a92ef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62565010"
---
# <a name="class-tab-window-properties-dialog-box"></a>Karta Třída, dialogové okno vlastnosti okna
Použití **třídy** karta zobrazuje informace ve třídě vybrané okno. Zobrazíte [dialogové okno Vlastnosti okna](../debugger/window-properties-dialog-box.md), přesuňte fokus [zobrazení Windows](../debugger/windows-view.md) okna. Vyberte jakékoli okno uzel ve stromu a pak zvolte **vlastnosti** z **zobrazení** nabídky.

 Následující nastavení jsou k dispozici na **třídy** kartu:

|Entry|Popis|
|-----------|-----------------|
|**Název třídy**|Název (nebo ordinální číslo) této třídy okna.|
|**Styly třídy**|Kombinace stylu kódů třídy.|
|**Bajty třídy**|Specifické pro aplikaci data přidružená k této třídy okna.|
|**Formát Atom třídy**|Atom pro třídu vrácené **RegisterClass** volání.|
|**Popisovač instance**|Popisovač instance modulu, který registrované třídy. Instance popisovače nejsou jedinečné.|
|**Bajty okna**|Počet bajtů navíc spojené s každou okno této třídy. Význam těchto bajtů se určuje podle aplikace. Rozbalte položku seznamu zobrazíte bajtové hodnoty ve formátu DWORD.|
|**Proces okna**|Aktuální adresu **WndProc** funkce pro windows z této třídy. Tím se liší od **proces okna** na **Obecné** kartě Pokud rozčlenění okna.|
|**Název nabídky**|Název hlavní nabídky, která souvisí s windows z této třídy ("none" Pokud neexistuje žádná nabídka).|
|**Popisovač ikony**|Popisovač ikony, která souvisí s windows z této třídy ("none" Pokud neexistuje žádná ikona).|
|**Popisovač ukazatele**|Popisovač pro kurzor, který je přidružený k windows této třídy ("none" Pokud neexistuje žádný kurzor).|
|**Bkgnd Brush**|Popisovač pro štětec pozadí, která souvisí s windows z této třídy, nebo jednu z předdefinovaných COLOR_ * barev pro vykreslování pozadí okna ("none" Pokud neexistuje žádný štětec).|