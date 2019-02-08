---
title: 'Návrhář postupu provádění – jak: Používání návrháře importů'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- System.Activities.Presentation.View.ImportDesigner.UI
ms.assetid: 61328ab6-9b66-4e12-8630-22e30ee8c9d1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: df041111bb452462c969995bacee97b08488d1c6
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55931959"
---
# <a name="how-to-use-the-imports-designer"></a>Postupy: Používání návrháře importů

Návrhář importů umožňuje zadejte obory názvů pro typy, které budete používat ve výrazech. Podobně jako **importuje** nebo **pomocí** klíčová slova v jazyce Visual Basic a C#, určení obory názvů v Návrhář importů umožňují jednoduše zadejte název typu ve výrazu spíše než plně Název typu kvalifikovaný verze.

Návrhář importů jsou reaguje na obě změny v uživatelském rozhraní a změny provedené při uložení pracovního postupu. Při uložení pracovního postupu, obory názvů může být automaticky přidán do návrháře importů. Patří mezi ně například:

- Obory názvů pro všechny typy použité v deklaracích proměnných a argumentů.

- Obory názvů pro všechny typy použité ve výrazech.

- Všechny ostatní obory názvů potřebné pro serializaci pracovního postupu (například oborů názvů používaných ve vlastní aktivity v pracovním postupu).

  Při uložení pracovní postup, můžete si všimnout, že některé obory názvů, který jste odstranili ručně jsou automaticky znovu přidat do návrháře importů z důvodu pravidla popsaná v předchozím seznamu.

## <a name="to-add-a-namespace-to-the-list-of-imported-namespaces"></a>Přidání nového oboru názvů na seznam importovaných oborů názvů

1.  Otevření aplikace služeb pracovního postupu WCF, konzolová aplikace pracovního postupu nebo projektu knihovny aktivity v sadě Visual Studio nebo aplikace pracovního postupu změněným hostováním.

2.  Klikněte na tlačítko **importy** v dolní části hlavního plátna. Zobrazí se Návrhář importů.

3.  Zadejte nebo vyberte z rozevíracího seznamu ovládacího prvku v horní části návrháře importů oboru názvů.

     Při psaní se zobrazí seznam platný obory názvů, které odpovídají zadané znaky.

4.  Stisknutím klávesy **Enter** do seznamu přidat obor názvů.

5.  Pokud chcete odebrat obor názvů v seznamu, vyberte obor názvů a potom stiskněte klávesu **odstranit** kláves na klávesnici. Všimněte si, že obor názvů můžete být odstraněno pouze tehdy, pokud obor názvů je neplatný z nějakého důvodu, například pokud sestavení, který obsahuje obor názvů je již odkazuje na projekt.