---
title: Příkazy, nabídek a panelů nástrojů | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus [Visual Studio SDK], commands
- commands [Visual Studio]
- toolbars [Visual Studio], commands
ms.assetid: 07b4ed90-dbbd-40df-b6c9-8395fd6f2ab6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6f27bfc7d679d972482e6b910f40a0ecf74d9d6a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="commands-menus-and-toolbars"></a>Příkazy, nabídek a panelů nástrojů
Nabídek a panelů nástrojů jsou způsobem uživatelé přístup k příkazům v vaší VSPackage. Příkazy jsou funkce, které provést úkoly, jako je například tisk dokumentu, aktualizovat zobrazení nebo vytvoření nového souboru. Nabídek a panelů nástrojů způsoby pohodlný grafické příkazech k dispozici pro uživatele. Související příkazy jsou obvykle Clusterované společně na stejném nabídky nebo panelu nástrojů.  
  
-   Nabídky se obvykle zobrazují jako řetězce jednoslovným clusteru v řádku v horní části integrované vývojové prostředí (IDE) nebo okno nástroje. Nabídky také lze zobrazit v důsledku události, klikněte pravým tlačítkem a jsou označovány jako místní nabídky v tomto kontextu. Při kliknutí na, rozbalte položku nabídky zobrazíte jeden nebo více příkazů. Příkazy, při kliknutí na, můžete provádět úlohy nebo spusťte dílčích, které obsahují další příkazy. Některé názvy dobře známé nabídky se souboru, upravit, zobrazení a oken. Další informace najdete v tématu [rozšíření nabídek a příkazů](../../extensibility/extending-menus-and-commands.md).  
  
-   Panely nástrojů jsou obvykle řádky tlačítek a jiných ovládacích prvků, jako je například pole se seznamem, seznamy, textová pole a nabídky řadiče. Všechny ovládací prvky panelu nástrojů jsou přidružené příkazy. Při kliknutí na tlačítko panelu nástrojů se aktivuje jeho přidružený příkaz. Tlačítka panelu nástrojů mají obvykle ikony, které naznačují základní příkazy, jako jsou tiskárny pro tisk příkaz. V ovládacím prvku rozevíracího seznamu je přidružen jiný příkaz každou položku v seznamu. Řadič nabídky je hybridní, ve kterém je jedné straně ovládacího prvku tlačítka panelu nástrojů a druhé straně je šipka dolů, která se zobrazí další příkazy při kliknutí na. Další informace najdete v tématu [přidáním řadiče nabídky na panel nástrojů](../../extensibility/adding-a-menu-controller-to-a-toolbar.md).  
  
-   Při vytváření příkazu také musíte vytvořit obslužnou rutinu události pro ni. Obslužné rutiny události Určuje, kdy příkaz je viditelný nebo povoleno, umožňuje změnit jeho text a zajišťuje náležitě reaguje příkazu ("trasy") Pokud je aktivován. Ve většině případů je IDE zpracovává příkazy, pomocí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní. Příkazy v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] trasy hierarchické uspořádání, počínaje kontext nejvnitřnější příkazů, na základě místní výběru a budete pokračovat ve nejkrajnější kontextu, a to na základě globální výběru. Příkazy, které jsou přidány do hlavní nabídky jsou okamžitě k dispozici pro skriptování. Další informace najdete v tématu [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md) a [výběr objektů kontextu](../../extensibility/internals/selection-context-objects.md).  
  
 Chcete-li definovat nové nabídek a panelů nástrojů, musí popisovat v souboru Visual Studio příkaz tabulky (.vsct). Šablona balíček Visual Studio vytvoří tento soubor, společně s elementy potřebné pro podporu ať příkazy, panely nástrojů a editory jste vybrali v šabloně. Alternativně můžete napsat svůj vlastní soubor .vsct pomocí schématu xml, který je popsaný tady: [referenční dokumentace schématu XML VSCT](../../extensibility/vsct-xml-schema-reference.md).  
  
 Další informace o práci se soubory .vsct najdete v tématu [tabulky příkaz Visual Studio (. Soubory Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
 Témata v této části popisují, jak fungují v VSPackages příkazy, nabídek a panelů nástrojů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Podrobný popis specifikace formátu příkaz tabulky.  
  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)  
 Popisuje na základě XML syntaxe a kompilátoru pro příkaz tabulky.  
  
 [Výchozí umístění příkazů, skupin a panelů nástrojů](../../extensibility/internals/default-command-group-and-toolbar-placement.md)  
 Popisuje předdefinované příkazy, skupin, nabídek a panelů nástrojů.  
  
 [Příkazy, nabídky a skupiny definované integrovaným vývojovým prostředím](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)  
 Určuje předdefinované nabídky, příkazy a příkaz skupin, které jsou k dispozici pro použití [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 [Návrh příkazu](../../extensibility/internals/command-design.md)  
 Vysvětluje, jak navrhnout příkazy.  
  
 [Optimalizace příkazů nabídky a panelu nástrojů](../../extensibility/internals/optimizing-menu-and-toolbar-commands.md)  
 Poskytuje pokyny pro příkazy.  
  
 [Zpřístupnění příkazů](../../extensibility/internals/making-commands-available.md)  
 Vysvětluje, jak k dispozici příkazy sady Visual Studio.  
  
 [Příkazy a nabídky, které používají spolupracující sestavení](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)  
 Vysvětluje, jak implementovat příkazy, které používají spolupráce – sestavení.  
  
## <a name="related-sections"></a>Související oddíly  
 [Směrování příkazů v balíčcích VSPackage](../../extensibility/internals/command-routing-in-vspackages.md)  
 Vysvětluje, směrování příkazů v VSPackages.