---
title: XAML chyby a upozornění | Microsoft Docs
ms.date: 03/06/2018
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 34eac8a0-7ec5-4c40-b97a-0126ed367931
author: karann-msft
ms.author: karann
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 072792b224d72e0f733373d56457a7a7667573fb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="xaml-errors-and-warnings"></a>XAML chyby a upozornění

Při vytváření XAML, Visual Studio analyzuje kód při psaní. Vlnovku se zobrazí na řádek kódu, když dojde k chybě. Ukazatele myši vlnovka získáte další informace o chybě nebo upozornění. Některé chyby a upozornění žárovek rychlé akce je zobrazení a pomocí **Ctrl**+**.** klávesové zkratky zobrazí možnosti vyřešit problém.

## <a name="error-types"></a>Typy chyb

Na pozadí několik nástrojů analyzovat XAML paralelně. Chyby jazyka XAML jsou rozdělené do jedné z následujících tří typů, založené na nástroj, který zjištěna chyba:

|**Chyba detekovaných službou**|**Formát kódu chyby**|  
|--------------------------------|-----------------|  
|Služba jazyka XAML (XAML editor)|XLSxxxx|  
|Návrhář XAML|XDGxxxx|  
|XAML upravit a pokračovat|XECxxxx|  

> [!Note]
> Ne všechny chyby a varování mají odpovídající kód. Tyto chyby jsou obvykle chyby návrháře XAML.


## <a name="suppress-xaml-designer-errors"></a>Potlačit chyby Návrhář XAML

Otevřete **možnosti** dialogové okno výběrem **nástroje > Možnosti**a potom vyberte **textový Editor > XAML > různé**.

Zrušte zaškrtnutí políčka **zobrazit chyby zjištěno pomocí návrháře XAML** zaškrtávací políčko.

![Návrhář XAML chyby potlačit](../designers/media/suppress_xaml_designer_errors.PNG "SuppressXAMLDesignerErrors")


