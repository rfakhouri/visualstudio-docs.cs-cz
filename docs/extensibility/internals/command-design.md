---
title: Příkaz návrhu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands
- commands, implementation
ms.assetid: 097108c3-f758-4b87-89d6-b32d12d9041a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 43b83e5a02fb84ad09531f87b3120168bad0b2e0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132168"
---
# <a name="command-design"></a>Příkaz návrhu
Když přidáte příkaz VSPackage, musíte zadat, kam se má zobrazit, když je k dispozici a jak je zpracovávat.  
  
## <a name="defining-commands"></a>Definování příkazy  
 Chcete-li definovat nové příkazy, můžete zahrňte soubor Visual Studio příkaz tabulky (.vsct) ve vašem projektu VSPackage. Pokud jste vytvořili VSPackage pomocí šablony balíček Visual Studio, tento projekt zahrnuje jednu z těchto souborů. Další informace najdete v tématu [tabulky příkaz Visual Studio (. Soubory Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
 Visual Studio sloučí všechny .vsct soubory, které najde, aby mohla zobrazovat příkazy. Protože tyto soubory se liší od VSPackage binární, není nutné načíst balíček, který chcete najít příkazy sady Visual Studio. Další informace najdete v tématu [jak VSPackages přidat prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
 Visual Studio použije <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> atribut registrace k definování nabídky prostředky a příkazy. Další informace najdete v tématu [implementace](../../extensibility/internals/command-implementation.md).  
  
 Příkazy lze změnit v době běhu v několika různými způsoby. Dají se zobrazí nebo skryté, povoleno nebo zakázáno. Můžete zobrazit různé text nebo ikony nebo obsahovat různé hodnoty. Značnou část přizpůsobení mohou být provedeny, než vaše VSPackage načte Visual Studio. Další informace najdete v tématu [jak VSPackages přidat prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
## <a name="command-handlers"></a>Obslužné rutiny příkazů  
 Při vytváření příkazu je nutné zadat obslužné rutiny události provedení příkazu. Pokud uživatel vybere příkaz, se musí být správně směrované. Směrování příkaz znamená odeslání správné VSPackage chcete povolit nebo zakázat, skrýt nebo ji zobrazit a provést, pokud se uživatel rozhodne Uděláte to tak. Další informace najdete v tématu [směrování algoritmus](../../extensibility/internals/command-routing-algorithm.md).  
  
## <a name="the-visual-studio-command-environment"></a>Příkaz prostředí Visual Studio  
 Visual Studio může hostovat libovolný počet VSPackages a každý můžete přispívat vlastní sadu příkazů. Prostředí zobrazí pouze příkazy, které jsou vhodné pro aktuální úlohy. Další informace najdete v tématu [dostupnosti](../../extensibility/internals/command-availability.md) a [výběr objektů kontextu](../../extensibility/internals/selection-context-objects.md).  
  
 VSPackage definující nové příkazy, nabídek, panely nástrojů nebo místní nabídky poskytuje jeho příkaz informace o sadě Visual Studio v průběhu instalace prostřednictvím položky registru, které odkazují na prostředky v nativní nebo spravovaný sestavení. Každý prostředek, pak odkazuje na soubor prostředků (.cto) na binární data, který se vytvoří při kompilaci Visual Studio příkaz tabulky (.vsct) souboru. To umožňuje poskytovat bez nutnosti načíst všechny nainstalované VSPackage sady sloučené příkazů, nabídek a panelů nástrojů sady Visual Studio.  
  
### <a name="command-organization"></a>Příkaz organizace  
 Prostředí umisťuje příkazy skupinou, prioritu a nabídky.  
  
-   Skupiny jsou logické kolekce související příkazy, například, **Vyjmout**, **kopie**, a **vložení** skupina příkazu. Skupiny jsou příkazy, které se zobrazují v nabídkách.  
  
-   Priorita určuje pořadí, ve kterém se zobrazují jednotlivé příkazy ve skupině v nabídce.  
  
-   Nabídky fungují jako kontejnery pro skupiny.  
  
 Prostředí predefines některé příkazy, skupiny a nabídky. Další informace najdete v tématu [výchozí příkaz, skupiny a umístění panelu nástrojů](../../extensibility/internals/default-command-group-and-toolbar-placement.md).  
  
 Příkaz lze přiřadit ke skupině primární. Určuje pozici příkazu v hlavní nabídce struktuře a v primární skupiny **přizpůsobit** dialogové okno. Příkaz se mohou objevit v několika skupin; příkaz může být například z hlavní nabídky, v místní nabídce a na panelu nástrojů. Další informace najdete v tématu [jak VSPackages přidat prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
### <a name="command-routing"></a>Směrování příkazů  
 Proces vyvolání a směrování příkazů pro VSPackages se liší od proces volání metod z instance objektů.  
  
 Prostředí směrování příkazů postupně z kontextu nejvnitřnější příkazu (místní), která je založena na aktuálním výběrem, kontext nejkrajnější (globální). První kontext, který se bude moct spustit příkaz je ten, který ji zpracovává. Další informace najdete v tématu [směrování algoritmus](../../extensibility/internals/command-routing-algorithm.md).  
  
 Ve většině případů je prostředí zpracovává příkazy pomocí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní. Vzhledem k tomu schéma směrování příkaz umožňuje mnoho různých objektů pro zpracování příkazů, <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> může být libovolný počet objektů implementované; tato patří Microsoft ActiveX – ovládací prvky, okno zobrazení implementace, objekty dokumentu, hierarchie projektu a VSPackage samotných objektech (pro globální příkazů). V některých případech specializované například směrování příkazů v hierarchii, <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> rozhraní musí být implementována.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Implementace](../../extensibility/internals/command-implementation.md)|Popisuje, jak implementovat příkazy v VSPackage.|  
|[Dostupnost](../../extensibility/internals/command-availability.md)|Popisuje, jak Visual Studio kontextu Určuje, které příkazy jsou k dispozici.|  
|[Směrování algoritmus](../../extensibility/internals/command-routing-algorithm.md)|Popisuje, jak Visual Studio příkaz směrování architektura umožňuje zpracovávat jiné VSPackages příkazy.|  
|[Pokyny pro umístění](../../extensibility/internals/command-placement-guidelines.md)|Navrhne, jak na pozici příkazy v prostředí Visual Studio.|  
|[Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)|Popisuje, jak můžete využívat VSPackages nejlépe příkaz architektura sady Visual Studio.|  
|[Výchozí umístění příkazů, skupin a panelů nástrojů](../../extensibility/internals/default-command-group-and-toolbar-placement.md)|Popisuje, jak můžete použít VSPackages nejlépe příkazy, které jsou zahrnuté v sadě Visual Studio.|  
|[Správa rozšíření VSPackages](../../extensibility/managing-vspackages.md)|Popisuje, jak načte VSPackages v sadě Visual Studio.|  
|[Soubory tabulek příkazů sady Visual Studio (.Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)|Poskytuje informace o formátu XML .vsct soubory, které se používají k popisu rozložení a vzhled příkazů v VSPackages.|