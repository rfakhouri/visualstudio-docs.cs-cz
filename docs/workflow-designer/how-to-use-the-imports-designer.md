---
title: 'Návrhář postupu provádění - postupy: použití návrháře importy'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Presentation.View.ImportDesigner.UI
ms.assetid: 61328ab6-9b66-4e12-8630-22e30ee8c9d1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de974ebba6fbe746a4d7acb4c1a20fefa5488a8e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-the-imports-designer"></a>Postupy: použití návrháře importy

Importy návrháře umožňuje zadejte obory názvů pro typy, které budete používat ve výrazech. Podobně jako **importuje** nebo **pomocí** klíčových slov v jazyce Visual Basic a C#, zadání obory názvů v Návrháři importy umožňují jednoduše zadejte ve výrazu a ne plně kvalifikovaný název typu Název typu verze.

Návrhář importy reaguje na obou změny v uživatelském rozhraní a změny provedené při uložení pracovního postupu. Při uložení pracovního postupu obory názvů může automaticky přidat do importy návrháře. Patří mezi ně například:

-   Obory názvů pro všechny typy používané v proměnné a argument deklarace.

-   Obory názvů pro všechny typy použít ve výrazech.

-   Všechny ostatní obory názvů požadované pro serializaci pracovního postupu (například oborů názvů používaných ve vlastních aktivit vyřadit v pracovním postupu).

 Při uložení pracovního postupu, můžete si všimnout, že některé obory názvů, které jste ručně odstranili nebudou automaticky znovu přidat, aby importy návrháře kvůli logiku popsané v předchozím seznamu.

## <a name="to-add-a-namespace-to-the-list-of-imported-namespaces"></a>Chcete-li přidat obor názvů do seznamu importovaných oborů názvů

1.  Otevřete aplikaci služby WCF pracovního postupu, pracovní postup konzolové aplikace nebo projektu knihovny aktivit v sadě Visual Studio 2010 nebo aplikace opětovné hostování nástroje pracovního postupu.

2.  Klikněte na tlačítko **importy** v dolní části hlavní plátno. Zobrazí se importuje návrháře.

3.  Zadejte nebo vyberte z ovládacího prvku rozevíracího seznamu v horní části návrháře importy oboru názvů.

     Jak budete zadávat, zobrazí se seznam platný obory názvů, které odpovídají zadané znaky.

4.  Stiskněte klávesu **Enter** přidat obor názvů do seznamu.

5.  Pokud chcete odebrat obor názvů v seznamu, vyberte obor názvů a potom stiskněte klávesu **odstranit** klíče na klávesnici. Všimněte si, obor názvů lze odstranit pouze v případě oboru názvů je neplatný z jakéhokoli důvodu třeba pokud je sestavení obsahující obor názvů je již odkazuje projektu.