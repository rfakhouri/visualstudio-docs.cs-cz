---
title: Mapy kódu jsou pomalé
ms.date: 05/16/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8f53376d1cff79dd69b7fb17704c4ddae8803c46
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55913181"
---
# <a name="improve-performance-for-code-maps"></a>Zvýšení výkonu pro mapy kódu

Při prvním generování mapu, Visual Studio indexuje všechny závislosti, které nalezne. Tento proces může trvat nějakou dobu, zvláště pro velká řešení, ale vyšší výkon. Pokud se změní kód, sada Visual Studio přeindexuje pouze aktualizovaný kód. Chcete-li minimalizovat čas potřebný pro mapování na dokončení vykreslování, zvažte následující návrhy:

- [Mapování závislostí, které vás zajímají.](#create-a-code-map-to-see-specific-dependencies)

- Před generováním mapy pro kompletní řešení snižte Rozsah řešení.

- Vypnout automatické sestavení pro řešení tak, že vyberete **přeskočení buildu** na panelu nástrojů mapy kódu.

- Vypnout automatické přidávání nadřazených položek tak, že vyberete **zahrnout nadřazené položky** na panelu nástrojů mapy kódu.

   ![Tlačítka pro přeskočení buildu a zahrnout nadřazené](../modeling/media/codemapsfilterskipbuildicons.png)

- Upravte soubor mapy kódu přímo na odebrání uzlů a odkazů, které nepotřebujete. Změna mapování neovlivní základní kód. V tématu [Přizpůsobení map kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).

Může trvat déle vytvářet mapy nebo přidávat položky do objektu map od **Průzkumníka řešení** při položku projektu **kopírovat do výstupního adresáře** je nastavena na **vždy Kopírovat**. Chcete-li zvýšit výkon, změňte tuto vlastnost na **kopírovat, pokud je novější** nebo `PreserveNewest`. Zobrazit [přírůstková sestavení](../msbuild/incremental-builds.md).

Dokončené mapa zobrazuje závislosti pouze pro kód úspěšně sestavené. Pokud dojde k chybám sestavení některých součástí, tyto chyby se zobrazí na mapě. Ujistěte se, že součást skutečně sestaví a má závislosti, než provedete rozhodnutí o architektuře založené na mapě.