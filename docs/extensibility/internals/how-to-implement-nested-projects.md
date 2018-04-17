---
title: 'Postupy: implementace vnořené projekty | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- nested projects, implementing
- projects [Visual Studio SDK], nesting
ms.assetid: d20b8d6a-f0e0-4115-b3a3-edda893ae678
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c90434fd8deae2f5f71c150759fc836b9ed43077
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-implement-nested-projects"></a>Postupy: implementace vnořené projekty
Při vytváření jsou typu vnořené projektu existuje několik dalších kroků, které musí být implementována. Nadřazený projekt přebírá některé stejné odpovědnosti, které má řešení pro jeho vnořená projekty. Nadřazený projekt je kontejner projekty podobná řešení. Konkrétně existují několik událostí, které musí být vyvolány řešení a projekty nadřazené vytvořit hierarchii vnořené projekty. Tyto události jsou popsané v následující proces pro vytváření vnořených projektů.

### <a name="to-create-nested-projects"></a>Chcete-li vytvořit vnořenou projekty

1.  Integrované vývojové prostředí (IDE) načte informace o souboru a spuštění projektu nadřazený projekt voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> rozhraní. Nadřazený projekt je vytvořen a přidán do řešení.

    > [!NOTE]
    >  V tomto okamžiku je příliš stará v procesu pro nadřazený projekt vytvořit vnořený projekt, protože nadřazený projekt je nutné vytvořit před vytvořením podřízené projekty. Toto pořadí nadřazený projekt můžete použít nastavení pro projekty podřízené a podřízené projekty můžete získat informace z nadřazené projektů v případě potřeby. Toto pořadí je, pokud je to nezbytné na klienty, jako je například Správa zdrojového kódu (SCC) a Průzkumníku řešení.

     Nadřazený projekt musí počkat <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren%2A> metoda má být volána IDE před jeho vnořené (podřízená) může vytvořit projekt nebo projekty.

2.  Volání IDE `QueryInterface` na nadřazený projekt pro <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject>. Pokud toto volání bude úspěšné, volání IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren%2A> metoda nadřazené otevřete všechny vnořené projekty pro nadřazený projekt.

3.  Volání nadřazený projekt <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnBeforeOpeningChildren%2A> metoda oznámit naslouchací procesy, které vnořené projekty se chystáte vytvořit. SCC, například naslouchá na tyto události vědět, pokud se vyskytnou kroků v procesu vytváření řešení a projektů v pořadí. Dojde-li kroky mimo pořadí, nemusí být řešení zaregistrován u zdrojového kódu správně.

4.  Volání nadřazený projekt <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AddVirtualProject%2A> metoda nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AddVirtualProjectEx%2A> metoda na všech jeho podřízených projekty.

     Předáte <xref:Microsoft.VisualStudio.Shell.Interop.__VSADDVPFLAGS> k `AddVirtualProject` metoda indikující, že virtuální projektu (vnořené) musí být přidaní do okna projekt vyloučen ze sestavení, přidá do správy zdrojového kódu a tak dále. `VSADDVPFLAGS` umožňuje ovládat viditelnost vnořený projekt a jaké funkce je k ní přidružena.

     Pokud jste znovu načíst dříve existující podřízené projektu, který má projektu GUID, které jsou uloženy v souboru projektu nadřazený projekt, volání nadřazený projekt `AddVirtualProjectEx`. Jediným rozdílem mezi `AddVirtualProject` a `AddVirtualProjectEX` je, že `AddVirtualProjectEX` má parametr, aby nadřazený projekt k určení každou instanci `guidProjectID` pro projekt podřízené povolit <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProjectOfGuid%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProjectOfProjref%2A> funkce správně.

     Pokud je k dispozici není žádný identifikátor GUID, například při přidání nového projektu vnořené řešení jeden pro projekt vytvoří v době, kdy se přidá do nadřazené. Je zodpovědností nadřazený projekt k uchování daného projektu GUID ve svém souboru projektu. Pokud odstraníte vnořený projekt, můžete taky odstranit identifikátor GUID pro tento projekt.

5.  Volání IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren> metodu na každý projekt podřízené nadřazeného projektu.

     Musí implementovat nadřazený projekt `IVsParentProject` Pokud budete chtít vnořit projekty. Ale nadřazený projekt nikdy volání `QueryInterface` pro `IVsParentProject` i v případě, že má nadřazený projekty pod ním. Řešení zpracovává volání `IVsParentProject` a, pokud je implementována, zavolá `OpenChildren` k vytváření vnořených projektů. `AddVirtualProjectEX` je vždy volat z `OpenChildren`. Nikdy by měla být volána nadřazený projekt zachování hierarchie vytvoření události v pořadí.

6.  Volání IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A> metoda na podřízené projektu.

7.  Volání nadřazený projekt <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnAfterOpeningChildren%2A> metoda oznámit naslouchací procesy vytvořený podřízené projekty pro nadřazený prvek.

8.  Volání IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnAfterOpenProject%2A> metoda na nadřazený projekt po všechny podřízené projekty jsou otevřené.

     Pokud již neexistuje, nadřazený projekt vytvoří identifikátor GUID pro každý projekt, vnořené voláním `CoCreateGuid`.

    > [!NOTE]
    >  `CoCreateGuid` je rozhraní API modelu COM volána, když je vytvořen identifikátor GUID. Další informace najdete v tématu `CoCreateGuid` a identifikátory GUID v knihovně MSDN.

     Nadřazený projekt ukládá tento identifikátor GUID v jeho souboru projektu mají být načteny příštím je otevřen v prostředí IDE. Podívejte se na krok 4 pro další informace týkající se volání z `AddVirtualProjectEX` načíst `guidProjectID` pro podřízené projekt.

9. <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> Metoda je volána poté pro nadřazený prvek ItemID podle konvence delegovat v vnořený projekt. <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> Načte vlastnosti uzlu, která je vnořena projekt, který chcete delegovat v, když je volána v nadřazené.

     Protože nadřazené a podřízené projekty instance prostřednictvím kódu programu, můžete nastavit vlastnosti pro vnořené projekty v tomto okamžiku.

    > [!NOTE]
    >  Pouze zobrazuje informace o kontextu z vnořené projektu, ale můžete také požádat, pokud nadřazený projekt má jakýkoliv kontext pro tuto položku kontrolou <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>. Tímto způsobem můžete přidat další atributy dynamické nápovědy a konkrétní možnosti nabídky do jednotlivých projektů vnořené.

10. V hierarchii je vytvořené pro zobrazení v Průzkumníku řešení pomocí volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetNestedHierarchy%2A> metoda.

     Předat hierarchii prostředí pomocí `GetNestedHierarchy` k vytvoření hierarchie pro zobrazení v Průzkumníku řešení. Tímto způsobem řešení zná projektu existuje a je možné spravovat pomocí Správce sestavení pro vytvoření nebo můžete povolit soubory v projektu k uvedení ve správě zdrojového kódu.

11. Vytvoření všechny vnořené projekty pro Project1 ovládací prvek je předán zpět do řešení a tento proces se opakuje pro projektu2.

     Tento stejný proces pro vytváření vnořených projektů dochází v podřízené projektu, který má podřízenou. V takovém případě pokud BuildProject1, která je podřízená Project1, měl podřízené projekty, měly by být vytvořeny po BuildProject1 a před projektu2. Proces je rekurzivní a hierarchii vychází shora dolů.

     Když je vnořený projekt zavřená, protože uživatel uzavřený řešení nebo konkrétní projektu samostatně, jinou metodu na `IVsParentProject`, <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.CloseChildren%2A>, je volána. Nadřazený projekt zabalí volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.RemoveVirtualProject%2A> metoda s <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeClosingChildren%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterClosingChildren%2A> metody pro naslouchací procesy pro řešení události upozornění, že dochází k uzavření vnořené projekty.

 V následujících tématech se zabývá několik konceptů, které je třeba zvážit při implementaci vnořené projekty:

 [Důležité informace pro uvolnění a opětovné načtení vnořených projektů](../../extensibility/internals/considerations-for-unloading-and-reloading-nested-projects.md)

 [Podpora průvodce pro vnořené projekty](../../extensibility/internals/wizard-support-for-nested-projects.md)

 [Implementace zpracování příkazů pro vnořené projekty](../../extensibility/internals/implementing-command-handling-for-nested-projects.md)

 [Filtrování dialogového okna Přidat položku pro vnořené projekty](../../extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects.md)

## <a name="see-also"></a>Viz také

- [Přidávání položek do dialogových oken Přidat novou položku](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)
- [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)
- [Kontrolní seznam: Vytvoření nových typů projektů](../../extensibility/internals/checklist-creating-new-project-types.md)
- [Kontextové parametry](../../extensibility/internals/context-parameters.md)
- [Soubor průvodce (.Vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)