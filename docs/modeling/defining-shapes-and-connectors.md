---
title: Definování obrazců a konektorů
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a24e447e5ec0b65635f7184bd0ae19b305edfdf8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62994622"
---
# <a name="define-shapes-and-connectors"></a>Definování obrazců a konektorů

Existuje několik typů základní tvary, které můžete použít k zobrazení informací v diagramu v jazyka specifického pro doménu (DSL).

## <a name="shapeTypes"></a> Základní typy obrazců a konektorů

DSL diagram ukazuje kolekci *tvary* vzájemně propojena těmito řádky nebo *konektory*. Obvykle, ale ne vždy:

- Tvary jsou viditelné reprezentace prvky modelu.

- Konektory představují vztahy odkazu.

- Diagram představuje instanci kořenovém modelu.

- Vkládání vztahy mezi elementy modelu jsou uvedeny ve členství ve skupině. Například prvků, která představuje součást porty jsou vložené v komponentě.

Tyto modely nejsou vynucená, ale jsou silněji podporovány. Při návrhu DSL berte v úvahu, který návrh vztahů obsažení by měl být ovlivněno způsob, jak mají být k dispozici modelu na obrazovce. Naopak referenční stavy by měly odrážet koncepty obchodní domény.

K dispozici jsou následující typy tvarů:

|Obrazec typu|Popis|
|-|-|
|Obrazec geometrie|Obecné účely obrazec obdélníkové nebo elipsy. Text a ikona dekoratéry můžete zobrazit v konkrétní pozici vzhledem k hranicím tvaru. Lze také vnořit tvary uvnitř obrazce geometrie.|
|Obrazec oddílu|Obdélník, který obsahuje hlavičky a obory, jako je třída UML. Každý oddíl může obsahovat seznam řádků textu.<br /><br /> Řádky představují obvykle prvky vložené v rámci elementu reprezentována tvaru. Příklad vytvoření DSL ze šablony řešení diagramy tříd.|
|Obrazec obrázku|Obrazec, který zobrazuje obrázek.|
|Tvar portu|Malý obdélník navržené tak, aby připojení k osnovy jiný tvar. Obvykle se používá v modelech komponenty.<br /><br /> Prvek modelu, který je reprezentován port je obvykle vložený pod element reprezentovaný nadřazeného obrazce. Příklad vytvoření DSL pomocí šablony řešení komponenty.<br /><br /> Ve výchozím nastavení můžete snímek obrazec portu spolu strany svého nadřazeného objektu. Můžete definovat pravidla hranice omezit na konkrétní pozici.<br /><br /> Tím, že obrazec portu velmi malé a transparentní, můžete ho poskytnout pevné spojovacího bodu na povrchu nadřazeného obrazce.|
|Plaveckých drah|Plaveckých drah diagramu rozdělit do segmentů vodorovně nebo svisle. Plavecké stále pod tvary v diagramu.<br /><br /> Obvykle jsou prvky modelu plavecké nadřazena na kořen modelu a další prvky jsou nadřazena na ně. Příklad vytvoření DSL ze šablony řešení tok úkolů.|
|Konektory|Čáry dekorace mezi tvary obvykle představují vztahy odkazu. Můžete nastavit možnosti, aby konektor přímá nebo Pravoúhlá a mají různé typy šipky.|

## <a name="shape-inheritance"></a>Tvar dědičnosti

Obrazce mohou dědit z jiného obrazce. Tvary však musí být stejného druhu. Například může dědit pouze obrazec geometrie z obrazec geometrie. Zděděné tvary mít oddíly a dekorátory jejich základní obrazec. Konektory mohou dědit z konektorů.