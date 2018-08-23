---
title: 'Postupy: používání návrháře importů | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ImportDesigner.UI
ms.assetid: 61328ab6-9b66-4e12-8630-22e30ee8c9d1
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: f1fc68f77e714efcd1d577cce6c988ef0943d71c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667265"
---
# <a name="how-to-use-the-imports-designer"></a>Postupy: používání návrháře importů
Návrhář importů umožňuje zadejte obory názvů pro typy, které budete používat ve výrazech. Podobně jako **importuje** nebo **pomocí** klíčových slov v jazyce Visual Basic .NET a C#, určení obory názvů v Návrhář importů umožňují jednoduše zadejte v výraz a ne plně kvalifikovaný název typu Název typu verze.  
  
 Návrhář importů jsou reaguje na obě změny v uživatelském rozhraní a změny provedené při uložení pracovního postupu. Při uložení pracovního postupu, obory názvů může být automaticky přidán do návrháře importů. Patří mezi ně například:  
  
-   Obory názvů pro všechny typy použité v deklaracích proměnných a argumentů.  
  
-   Obory názvů pro všechny typy použité ve výrazech.  
  
-   Všechny ostatní obory názvů potřebné pro serializaci pracovního postupu (například oborů názvů používaných ve vlastní aktivity v pracovním postupu).  
  
 Při uložení pracovní postup, můžete si všimnout, že některé obory názvů, který jste odstranili ručně jsou automaticky znovu přidat do návrháře importů z důvodu pravidla popsaná v předchozím seznamu.  
  
### <a name="to-add-a-namespace-to-the-list-of-imported-namespaces"></a>Přidání nového oboru názvů na seznam importovaných oborů názvů  
  
1.  Otevření aplikace služeb pracovního postupu WCF, konzolová aplikace pracovního postupu nebo projekt knihovny aktivit v [!INCLUDE[vs2010](../includes/vs2010-md.md)] nebo aplikace pracovního postupu změněným hostováním.  
  
2.  Klikněte na tlačítko **importy** v dolní části hlavního plátna. Zobrazí se Návrhář importů.  
  
3.  Zadejte nebo vyberte z rozevíracího seznamu ovládacího prvku v horní části návrháře importů oboru názvů.  
  
     Při psaní se zobrazí seznam platný obory názvů, které odpovídají zadané znaky.  
  
4.  Stisknutím klávesy **Enter** do seznamu přidat obor názvů.  
  
5.  Pokud chcete odebrat obor názvů v seznamu, vyberte obor názvů a potom stiskněte klávesu **odstranit** kláves na klávesnici. Všimněte si, že obor názvů můžete být odstraněno pouze tehdy, pokud obor názvů je neplatný z nějakého důvodu, například pokud sestavení, který obsahuje obor názvů je již odkazuje na projekt.