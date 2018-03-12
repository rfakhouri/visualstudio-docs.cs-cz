---
title: "Procházet a vyberte typ dialogové okno .NET | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TypeBrowser.UI
- ActivityTypeResolver.UI
ms.assetid: 864b60b6-a070-4e5c-aa5b-a25341b57ea6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 33e2ba5ff213c2bdd2684d72f411b172c0437c99
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="browse-and-select-a-net-type-dialog-box"></a>Procházet a vyberte dialogové okno typ rozhraní .NET

V **vlastnosti** oken, dialogových oken nebo návrháře například návrháře proměnné, když vyberete **Procházet pro typy...**  ze seznamu datových typů, je **Procházet a vyberte typ formátu .NET** dialogové okno (uvedené ve zkrácené formě jako "typ prohlížeče"). V tomto dialogovém můžete typu ze sestavení a projektů zobrazení stromu.

 Toto dialogové okno je vzhledem k počtu uživatelských scénářů, včetně následujících:

-   Při nastavování typ proměnné nebo argumentu.

-   Při výběru typu Obecné aktivity.

-   Při přidávání catch na <xref:System.Activities.Statements.TryCatch> aktivity.

> [!NOTE]
> Typ prohlížeče můžete zobrazit typy jazyka Visual Basic Vícenásobná pole, ale není multidimenzionálního pole typů. V tématu [Vícenásobná pole](http://go.microsoft.com/fwlink/?LinkId=195226) a [vícerozměrná pole](http://go.microsoft.com/fwlink/?LinkId=195227) podrobnosti.

## <a name="selecting-a-value-or-reference-type-from-the-type-browser"></a>Výběr hodnotu nebo odkaz na typ z typu prohlížeče

#### <a name="to-select-a-value-or-reference-type-from-the-type-browser"></a>Vyberte hodnotu nebo odkaz na typ z typu prohlížeče

1.  V **název typu** zadejte název tohoto typu, který chcete použít.

2.  Proveďte jednu z těchto akcí:

    -   Jakmile se zobrazí název typu, který chcete používat ve stromu v **název typu** pole, dvakrát klikněte na typ ji vyberte.

    -   Zadejte dostatečný počet znaků **název typu** políčko k jednoznačné identifikaci typ, který chcete použít, a stiskněte klávesu enter a vyberte typ

#### <a name="to-select-a-generic-type-from-the-type-browser"></a>Vyberte z prohlížeče typ obecného typu

1.  V **název typu** pole, zadejte název typu, který chcete použít.

2.  Jakmile se zobrazí název typu, který chcete používat ve stromu v **název typu** pole, klikněte na typ ji způsobí rozevíracích seznamech vyberte zobrazí.

     Vyberte typ, který chcete použít zavřete obecná z rozevíracího seznamu polí, a pak klikněte na **OK**.

## <a name="types-displayed-in-the-type-browser"></a>Typy zobrazení v prohlížeči typu
 Typy zobrazení v prohlížeči typu se může lišit v závislosti na tom, jak byla spuštěná typu prohlížeče. Pokud typ prohlížeče byl spuštěn z projektu workflow uvnitř **vs2010**, ve výchozím nastavení všechny typy v odkazovaných sestaveních a odkazované projekty jsou zobrazeny. Pokud typ prohlížeče byl spuštěn z mimo **vs2010** projektu systému (například jako aplikace opětovné hostování nástroje pracovního postupu nebo v samostatné souboru pracovního postupu), pak ve výchozím nastavení jsou uvedeny typy ze všech sestavení načíst do domény aplikace .

 Typy v prohlížeči typ lze filtrovat pomocí návrháře vývojáři aktivity. Pro danou aktivitu může se zobrazit pouze podmnožinu typy. Například v <xref:System.Activities.Statements.TryCatch> aktivity, pouze typy odvozené od <xref:System.Exception> se zobrazují v prohlížeči typu.

## <a name="filtering-search-results-in-the-type-browser"></a>Filtrování výsledků hledání v prohlížeči typu
 Seznam typů v **název typu** pole získá kratší jako typ více znaků, aby byla nalezena shoda. V seznamu Filtrované se zobrazí pouze typy jejichž plně kvalifikovaný název začíná řetězec, který jste zadali, nebo jejichž krátký název začíná řetězec, který jste zadali.

 Příklad:

1.  Zadáním **operace** odpovídá <xref:System.OperationCanceledException> ale ne <xref:System.InvalidOperationException>. Tak, aby odpovídaly <xref:System.InvalidOperationException>, začněte psát System.I nebo neplatná.

2.  Zadáním **Obecné** odpovídá <xref:System.GenericUriParser> , ale není typy v <xref:System.Collections.Generic> oboru názvů. K vyhledání typů v <xref:System.Collections.Generic> obor názvů, typ plně kvalifikovaný název oboru názvů.

## <a name="selecting-a-service-contract-using-the-type-browser-dialog"></a>Výběr kontraktu služby pomocí dialogového okna prohlížeče typu
 Při výběru typu kontraktu služby, typ prohlížeče se zobrazí pouze typy, které mají <xref:System.ServiceModel.ServiceContractAttribute> atribut.

## <a name="see-also"></a>Viz také

- [Používání návrhářů aktivit](../workflow-designer/using-the-activity-designers.md)