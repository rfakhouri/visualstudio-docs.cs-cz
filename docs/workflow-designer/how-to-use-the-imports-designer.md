---
title: 'Postupy: použití návrháře importy | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ImportDesigner.UI
ms.assetid: 61328ab6-9b66-4e12-8630-22e30ee8c9d1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 94b55e4b9f7f2b1d4e571b11fcdc4fba4d4f6754
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-the-imports-designer"></a>Postupy: použití návrháře importy
Importy návrháře umožňuje zadejte obory názvů pro typy, které budete používat ve výrazech. Podobně jako **importuje** nebo **pomocí** klíčových slov v jazyce Visual Basic a C#, zadání obory názvů v Návrháři importy umožňují jednoduše zadejte ve výrazu a ne plně kvalifikovaný název typu Název typu verze.  
  
 Návrhář importy reaguje na obou změny v uživatelském rozhraní a změny provedené při uložení pracovního postupu. Při uložení pracovního postupu obory názvů může automaticky přidat do importy návrháře. Patří mezi ně například:  
  
-   Obory názvů pro všechny typy používané v proměnné a argument deklarace.  
  
-   Obory názvů pro všechny typy použít ve výrazech.  
  
-   Všechny ostatní obory názvů požadované pro serializaci pracovního postupu (například oborů názvů používaných ve vlastních aktivit vyřadit v pracovním postupu).  
  
 Při uložení pracovního postupu, můžete si všimnout, že některé obory názvů, které jste ručně odstranili nebudou automaticky znovu přidat, aby importy návrháře kvůli logiku popsané v předchozím seznamu.  
  
### <a name="to-add-a-namespace-to-the-list-of-imported-namespaces"></a>Chcete-li přidat obor názvů do seznamu importovaných oborů názvů  
  
1.  Otevřete aplikaci služby WCF pracovního postupu, pracovní postup konzolové aplikace nebo projektu knihovny aktivit v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] nebo aplikace opětovné hostování nástroje pracovního postupu.  
  
2.  Klikněte na tlačítko **importy** v dolní části hlavní plátno. Zobrazí se importuje návrháře.  
  
3.  Zadejte nebo vyberte z ovládacího prvku rozevíracího seznamu v horní části návrháře importy oboru názvů.  
  
     Jak budete zadávat, zobrazí se seznam platný obory názvů, které odpovídají zadané znaky.  
  
4.  Stiskněte klávesu **Enter** přidat obor názvů do seznamu.  
  
5.  Pokud chcete odebrat obor názvů v seznamu, vyberte obor názvů a potom stiskněte klávesu **odstranit** klíče na klávesnici. Všimněte si, obor názvů lze odstranit pouze v případě oboru názvů je neplatný z jakéhokoli důvodu třeba pokud je sestavení obsahující obor názvů je již odkazuje projektu.