---
title: XAML chyby a upozornění
ms.date: 03/06/2018
ms.topic: conceptual
ms.assetid: 34eac8a0-7ec5-4c40-b97a-0126ed367931
author: karann-msft
ms.author: karann
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d3ae795b464d8a693371b1ebb9238a897debbf02
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62892615"
---
# <a name="xaml-errors-and-warnings"></a>Chyby a upozornění XAML

Při vytváření obsahu XAML, sada Visual Studio analyzuje při psaní kódu. Vlnovku se zobrazí na řádku kódu, když dojde k chybě. Ukazatel myši piktogram obsahuje bližší informace o chybě nebo upozornění. Některé chyby a upozornění žárovky rychlá akce je zobrazení a použití **Ctrl**+**.** stiskněte kombinaci kláves zobrazí možnosti k vyřešení problému.

## <a name="error-types"></a>Typy chyb

Na pozadí analyzovat více nástrojů pro XAML paralelně. Chyby XAML jsou rozdělené do jedné z následujících tří typů, založené na nástroj, který se zjistila Chyba:

|**Detekoval chybu**|**Formát kódu chyby**|
| - |-----------------|
|Služba jazyka XAML (editoru XAML)|XLSxxxx|
|Návrhář XAML|XDGxxxx|
|XAML upravit a pokračovat|XECxxxx|

> [!Note]
> Ne všechny chyby nebo upozornění mají odpovídající kód. Tyto chyby jsou obvykle chyby návrháře XAML.

## <a name="suppress-xaml-designer-errors"></a>Potlačit chyby návrháře XAML

Otevřít **možnosti** dialogové okno tak, že vyberete **nástroje > Možnosti**a pak vyberte **textový Editor > XAML > různé**.

Zrušte zaškrtnutí políčka **zobrazit chyby zjištěné návrhářem XAML** zaškrtávací políčko.

![Potlačit chyby návrháře XAML](../designers/media/suppress_xaml_designer_errors.png)
