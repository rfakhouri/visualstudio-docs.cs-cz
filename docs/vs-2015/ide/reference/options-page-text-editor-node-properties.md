---
title: Stránka Možnosti, vlastnosti uzlu textový Editor | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Tools Options settings, Text Editor node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 19438302-0677-4f4d-9720-5667e6a22ab2
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d127aaa85cdd8da9e5daebe5c7841e0f6e85238d
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65674878"
---
# <a name="options-page-text-editor-node-properties"></a>Stránka Možnosti, vlastnosti uzlu textového editoru
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Tento dokument popisuje některé stránky (nebo kolekce vlastností), které jsou přidruženy **textový Editor** kategorie, `DTE.Properties("TextEditor", <Property Page>)`, nástroje **možnosti** dialogové okno. Název každého pododdílu je volání, které slouží k přístupu `Properties` kolekce a v tabulce v každém pododdílu jsou uvedeny vlastnosti v kolekci.  
  
 Makra jazyka Visual Basic v [Controlling Options Settings](https://msdn.microsoft.com/library/a09ed242-7494-4cde-bbd1-7a8ec617965d) ukazují, jak zobrazit aktuální možnosti a jejich hodnoty pro každou stránku **možnosti** dialogové okno.  
  
## <a name="general"></a>Obecné  
 `DTE.Properties("TextEditor", "General")`  
  
|Název položky vlastnosti|Value|Popis|  
|------------------------|-----------|-----------------|  
|GoToAnchorAfterEscape|Get/Set (Boolean)|Pokud `True`, stiskněte escape při výběru způsobí, že kurzor přesunout do kterého byla spuštěna akce, která vytvořila tento výběr. `False` Přesune kurzor na konec výběru.|  
|DragNDropTextEditing|Get/Set (Boolean)|Určuje, zda lze při operacích kopírování nebo vyjmutí a vložení vybranou oblast textu přetáhnout v dokumentu z jednoho místa do jiného.|  
|HorizontalScrollBar|Get/Set (Boolean)|Určuje, zda se v oknech editoru zobrazuje vodorovný posuvník.|  
|VerticalScrollBar|Get/Set (Boolean)|Určuje, zda se v oknech editoru zobrazuje svislý posuvník.|  
|SelectionMargin|Get/Set (Boolean)|Určuje, zda je na levé straně podokna textu místo pro speciální operace výběru, ikony pro kreslení zarážek atd.|  
|MarginIndicatorBar|Get/Set (Boolean)|Určuje, zda se zobrazuje svislá čára, která odděluje levý okraj podokna textu od hlavní části tohoto podokna.|  
|UndoCaretActions|Get/Set (Boolean)|If `True`. operace vrácení zpět zahrnují přesunutí kurzoru, výběrové příkazy a tak dále, kromě editačních akcí, které mění vyrovnávací paměť.|  
|AutoDelimiterHighlighting|Get/Set (Boolean)|Určuje, zda při zadání koncového oddělovače zvýrazní editor počáteční oddělovač. Editor vždy zobrazí počáteční oddělovač tučně bez ohledu na hodnotu této vlastnosti.|  
|EditorEmulation|Get/Set (Enum)||  
|DetectUTF8WithoutSignature|Get/Set (Boolean)|Zjistí, zda soubor používá kódování UTF-8, pokud nemá signaturu kódování.|  
|TrackChanges|Get/Set (Boolean)||  
  
## <a name="plain-text"></a>Prostý text  
 `DTE.Properties("TextEditor", "PlainText")`  
  
 `PlainText` Možnosti editoru ovlivňují nastavení editoru při úpravě textových souborů. Každý programovací jazyk a [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] balíček má své vlastní zvláštní **textový Editor** nastavení. Například k zobrazení nebo změna [!INCLUDE[csprcs](../../includes/csprcs-md.md)] použít nastavení editoru `DTE.Properties("TextEditor", "CSharp") or DTE.Properties("TextEditor", "CSharp-Specific")`. Pro **skript SQL** použít nastavení editoru `DTE.Properties("TextEditor", "SQL ")`.  
  
|Název položky vlastnosti|Value|Popis|  
|------------------------|-----------|-----------------|  
|AutoListMembers|Get/Set (Boolean)|Určuje, zda se automaticky zobrazí dostupný seznam členů, když uživatel zadá za odkaz na proměnnou tečku.|  
|AutoListParams|Get/Set (Boolean)|Určuje, zda se automaticky zobrazí popis seznamu argumentů, když uživatel zadá za název funkce závorku (.|  
|HideAdvancedMembers|Get/Set (Boolean)|Určuje, zda se mají v seznamech doplňování výrazů vypisovat všechny členy nebo pouze nejpoužívanější.|  
|VirtualSpace|Get/Set (Boolean)|Určuje, zda se prázdné znaky zobrazují jako grafika. Nastavení na `true` způsobí, že `WordWrap` vlastnost položky (v tomto seznamu) nastavit `false`.|  
|WordWrap|Get/Set (Boolean)|Určuje, zda se dlouhé řádky v tomto zobrazení zalamují na hranicích slov. Nastavení na `true` způsobí, že `VirtualSpace` vlastnost položky (v tomto seznamu) nastavit `false`.|  
|WordWrapGlyphs|Get/Set (Boolean)|Zobrazí piktogram na konci řádku; označuje, že se tento řádek zalamuje na další řádek.|  
|EnableLeftClickForURLs|Get/Set (Boolean)|Určuje, zda editor podtrhuje adresy URL a umožňuje v systémem zaregistrovaném webovém prohlížeči přejít na tuto adresu URL jedním kliknutím.|  
|IndentStyle|Získá nebo nastaví (<xref:EnvDTE.vsIndentStyle>)|Určuje styl odsazení: Výchozí, inteligentní nebo žádné.|  
|TabSize|Get/Set (Long)|Představuje počet mezer pro tabulátor. Nastavení celého čísla mimo rozsah 1–60 (včetně) se nezdaří.|  
|InsertTabs|Get/Set (Boolean)|Pokud `True`, při odsazení použijí znaky TABULÁTORU.|  
|IndentSize|Get/Set (Long)|Představuje počet mezer pro jednu úroveň odsazení. Nastavení celočíselné hodnoty mimo rozsah 1–60 (včetně) se nezdaří.|  
|ShowLineNumbers|Get/Set (Boolean)|Určuje, zda se při zobrazení dokumentu v základním editoru zobrazují na levém okraji čísla řádků.|  
|ShowNavigationBar|Get/Set (Boolean)|Určuje, zda se v horní části oken editoru zobrazují rozevírací seznamy a tlačítka.|  
|CutCopyBlankLines|Get/Set (Boolean)|Vyjme nebo zkopíruje prázdné řádky, pokud jsou vybrány.|  
  
## <a name="see-also"></a>Viz také  
 [Řízení nastavení možností](https://msdn.microsoft.com/library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Určování názvů položky vlastností na stránkách možností](https://msdn.microsoft.com/library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Stránka Možnosti, vlastnosti uzlu prostředí](../../ide/reference/options-page-environment-node-properties.md)   
 [Stránka Možnosti, vlastnosti uzlu Písma a barvy](../../ide/reference/options-page-fonts-and-colors-node-properties.md)
