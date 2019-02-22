---
title: Ladění zdroje souborů, společná nastavení řešení vlastnost dialogového okna stránky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.options.FindSource
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Debug Source Files property page
- debugging [Visual Studio], specifying source and symbol files
- source files, specifying in debugger
- debugger, source files
ms.assetid: 0af11464-eeb1-4d0b-87a6-0cc96779afb1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83bed0588a0959ab85906d949e1b0752396223ae
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56609706"
---
# <a name="debug-source-files-common-properties-solution-property-pages-dialog-box"></a>Ladění zdrojových souborů, společná nastavení, dialogové okno stránek vlastností řešení
Tuto stránku vlastností určuje, kde ladicí program vyhledá zdrojové soubory při ladění řešení.

 Pro přístup **zdrojové soubory ladění** stránky vlastností, klikněte pravým tlačítkem na řešení v **Průzkumníka řešení** a vyberte **vlastnosti** z místní nabídky. Rozbalte **společné vlastnosti** složky a klikněte na tlačítko **zdrojové soubory ladění** stránky.

 **Adresáře obsahujícího zdrojový kód** obsahuje seznam adresářů, ve kterých ladicí program vyhledává zdrojové soubory při ladění řešení. Vyhledávají také podadresáře zadaných adresářích.

 **Nehledat tyto zdrojové soubory** zadejte názvy všech souborů, které nechcete, aby ladicí program ke čtení. Pokud ladicí program nalezne některý z těchto souborů v jednom z adresářů zadaných výše, se bude ignorovat. Pokud **najít zdroj** dialogové okno se zobrazí při ladění a kliknutí na **zrušit**, tak, aby ladicí program nebude pokračovat ve vyhledávání pro tento soubor získá do tohoto seznamu přidat soubor jste hledali.

## <a name="see-also"></a>Viz také

- [Zabezpečení ladicího programu](../debugger/debugger-security.md)
- [Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)