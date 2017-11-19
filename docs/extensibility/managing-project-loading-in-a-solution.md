---
title: "Správa projektu načítání v řešení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: solutions, managing project loading
ms.assetid: 097c89d0-f76a-4aaf-ada9-9a778bd179a0
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b28db42e17e95ea7c354f5ba4d7b0c231c2d2fe5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="managing-project-loading-in-a-solution"></a>Správa načítání projektu v řešení
Řešení sady Visual Studio může obsahovat velké množství projekty. Výchozí chování sady Visual Studio je načíst všechny projekty v řešení v době, kdy je řešení otevřené a nechcete povolit uživateli přístup k žádným z projektů všechny z nich nedokončili načítání. Při procesu načítání projektu bude poslední více než dvě minuty, se zobrazí indikátor průběhu zobrazující počet projekty načíst a celkový počet projekty. Uživatel může mít za následek uvolnění projekty při práci s řešení s více projekty, ale tento postup má některé nevýhody: odpojen projekty nejsou vytvořené jako součást příkazu znovu sestavit řešení a popisy IntelliSense typů a členů uzavřený projekty nejsou zobrazeny.  
  
 Vývojáři můžou snížit zatížení doby řešení a spravovat projektu načítání chování vytvořením řešení zatížení správce. Správce zatížení řešení můžete nastavit jiný projekt načítání priority pro konkrétní projekty nebo typy projektů, ujistěte se, zda jsou načteny projekty před zahájením pozadí sestavení, zpoždění pozadí načítání, dokud nebudou dokončeny jiné úlohy na pozadí a provádění Další úlohy správy zatížení projektu.  
  
## <a name="project-loading-priorities"></a>Načítání priority projektu  
 Visual Studio definuje čtyři jiný projekt načítání priority:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>(výchozí): Po otevření řešení projekty jsou načteny asynchronně. Pokud tato priorita je nastavena na odpojen projektu po řešení je již otevřeno, projekt bude načten na další bod nečinnosti.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: Po otevření řešení projekty jsou načteny na pozadí, které uživateli umožňují přístup k projektů, jako jsou načteny bez nutnosti počkat, dokud se načtou všechny projekty.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: projekty se načtou při jsou přístupná. Projekt se otevře, když uživatel rozšíří na uzel projektu v Průzkumníku řešení klikněte po otevření souboru, které patří do projektu po otevření řešení, protože je v seznamu otevřít dokument (uchovávané v souboru možnosti uživatele na řešení), nebo když jiného projektu To znamená načítá má závislost na projekt. Tento typ projektu není automaticky načíst před zahájením procesu sestavení; Správce zatížení řešení je odpovědný za dodržování, zda jsou načteny všechny potřebné projekty. Tyto projekty by měly být načteny také před zahájením vyhledání a nahrazení v souborech mezi celé řešení.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: projekty mají není možné načíst, pokud uživatel výslovně požaduje. To je případ, kdy nejsou explicitně odpojen projekty.  
  
## <a name="creating-a-solution-load-manager"></a>Vytváření řešení zatížení manager  
 Vývojáři můžou vytvářet řešení zatížení manager implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager> a poradenství Visual Studio, že správce zatížení řešení je aktivní.  
  
#### <a name="activating-a-solution-load-manager"></a>Aktivace správce zatížení řešení  
 Visual Studio umožňuje pouze jeden správce zatížení řešení v daném okamžiku, musíte poradit Visual Studio, pokud chcete aktivovat zatížení řešení správce. Pokud později na aktivaci druhý správce zatížení řešení bude odpojen správce zatížení vašeho řešení.  
  
 Musíte získat <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution> služby a nastavte <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> vlastnost:  
  
```csharp  
IVsSolution pSolution = GetService(typeof(SVsSolution)) as IVsSolution;  
object objLoadMgr = this;   //the class that implements IVsSolutionManager  
pSolution.SetProperty((int)__VSPROPID4.VSPROPID_ActiveSolutionLoadManager, objLoadMgr);  
```  
  
#### <a name="implementing-ivssolutionloadmanager"></a>Implementace IVsSolutionLoadManager  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager.OnBeforeOpenProject%2A> Metoda je volána při otevírání řešení. Chcete-li tuto metodu implementovat, použijte <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManagerSupport> služby nastavit prioritu zatížení typu projektu, které chcete spravovat. Následující kód například nastaví C# typy projektů načíst na pozadí:  
  
```csharp  
Guid guidCSProjectType = new Guid("{FAE04EC0-301F-11d3-BF4B-00C04F79EFBC}");  
pSLMgrSupport.SetProjectLoadPriority(guidProjectID, (uint)_VSProjectLoadPriority.PLP_BackgroundLoad);  
```  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager.OnDisconnect%2A> Metoda je volána, když Visual Studio se právě vypíná nebo když se jiný balíček trvá jako správce zatížení aktivním řešení voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.SetProperty%2A> s <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> vlastnost.  
  
#### <a name="strategies-for-different-kinds-of-solution-load-manager"></a>Strategie pro různé druhy správce zatížení řešení  
 Správci zatížení řešení můžete implementovat různými způsoby v závislosti na typech řešení, která jsou určená ke správě.  
  
 Pokud správce zatížení řešení slouží ke správě řešení načítání obecně, se dá implementovat jako součást VSPackage. Balíček musí být nastavena na autoload přidáním <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> na VSPackage s hodnotou <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionOpening_guid>. Správce zatížení řešení můžete za aktivuje <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda.  
  
> [!NOTE]
>  Další informace o balíčcích autoloading najdete v tématu [načítání VSPackages](../extensibility/loading-vspackages.md).  
  
 Vzhledem k tomu, že Visual Studio rozpozná pouze poslední řešení zatížení správce chcete aktivovat, musí správce zatížení obecné řešení vždy zjistí, zda je před aktivací sami existující správce zatížení. Pokud ve službě řešení pro volání metody GetProperty() <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> vrátí `null`, neexistuje žádný správce zatížení aktivním řešení. Pokud není vrátit hodnotu null, zkontrolujte, zda je objekt stejný jako správce zatížení vašeho řešení.  
  
 Pokud správce zatížení řešení slouží ke správě pouze několik typů řešení, VSPackage mohou přihlásit k odběru událostí načítání řešení (voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A>) a použijte obslužnou rutinu události pro <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A> aktivovat správce zatížení řešení.  
  
 Pokud správce zatížení řešení slouží ke správě pouze konkrétní řešení, můžete informace o aktivaci trvalé jako součást soubor řešení. Chcete-li to provést, volejte <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> pro oddíl předběžné řešení.  
  
 Správci zatížení specifického řešení by měl deaktivovat sami v <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents.OnAfterCloseSolution%2A> obslužné rutiny události, aby se v konfliktu s jiným správcům zatížení řešení.  
  
 Pokud potřebujete řešení zatížení správce pouze pro udržení zatížení priority globální projektu (například vlastnosti nastavit na stránce Možnosti), můžete si aktivovat správce zatížení řešení v <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A> obslužné rutiny události, zachovat nastavení pak ve vlastnostech řešení Deaktivujte správce zatížení řešení.  
  
## <a name="handling-solution-load-events"></a>Zpracování událostí zatížení řešení  
 K odběru událostí načítání řešení, volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A> Když aktivujete správce zatížení vašeho řešení. Pokud implementujete <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents>, můžete reakce na události, které se vztahují na jiný projekt načítání priority.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A>: Toto je vyvolána před otevřením řešení. Můžete ho Pokud chcete změnit projekt, načítání prioritu pro projekty v řešení.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeBackgroundSolutionLoadBegins%2A>: Toto je aktivováno po řešení, které je zcela načten, ale před pozadí projektu načítání začne počítat od začátku. Například uživatel mohl získat přístup k projektu, jehož priorita zatížení je LoadIfNeeded nebo správce řešení zatížení mohlo změnit prioritu zatížení projektu na BackgroundLoad, který by měl začínat pozadí zatížení tohoto projektu.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterBackgroundSolutionLoadComplete%2A>: Toto je aktivována například po začátku plně načtení řešení, zda manažera zatížení řešení. Také je aktivována, po načtení pozadí nebo vyžádání načíst vždy, když se stane úplným načtením řešení. Ve stejnou dobu <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExistsAndFullyLoaded_guid> opětovné aktivaci.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnQueryBackgroundLoadProjectBatch%2A>: Toto je vyvolána před načtením projektu (nebo projekty). Chcete-li zajistit, že jiné procesy na pozadí jsou dokončeny před projektů jsou načteny, nastavte `pfShouldDelayLoadToNextIdle` k **true**.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeLoadProjectBatch%2A>: Toto je aktivována, jestliže dávky projekty je možné načíst. Pokud `fIsBackgroundIdleBatch` má hodnotu true, projektů se mají načíst na pozadí; Pokud `fIsBackgroundIdleBatch` je nastavena hodnota false, projekty, které mají být načteny synchronně jako výsledek požadavku na uživatele, například pokud uživatel rozšíří čeká na projekt v Průzkumníku řešení. Můžete to udělat nákladné práci, kterou v opačném případě by bylo potřeba provést implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterLoadProjectBatch%2A>: Toto je aktivováno po dávky projekty se načetl.  
  
## <a name="detecting-and-managing-solution-and-project-loading"></a>Zjišťování a Správa řešení a načítání projektu  
 Aby bylo možné zjistit stav zatížení projekty a řešení, volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProperty%2A> s následujícími hodnotami:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` vrátí `true` Pokud všechny své projekty a řešení se načtou, jinak `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` vrátí `true` Pokud dávky projekty aktuálně během načítání na pozadí, jinak `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` vrátí `true` Pokud dávky projekty jsou aktuálně načítá synchronně v důsledku příkaz uživatele nebo jiných explicitní zatížení, jinak `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID2>: `var` vrátí `true` Pokud řešení aktuálně dochází k uzavření, jinak `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>: `var` vrátí `true` Jestliže řešení je aktuálně otevíráte, jinak `false`.  
  
 Můžete také zajistit, že jsou načtená projekty a řešení (bez ohledu na to, co jsou priority zatížení projektů) při volání jedné z následujících metod:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureSolutionIsLoaded%2A>: voláním této metody vynutí projekty v řešení pro načtení předtím, než se vrátí tato metoda hodnotu.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectIsLoaded%2A>: voláním této metody vynutí projekty v `guidProject` načíst než metoda vrátí.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectsAreLoaded%2A>: voláním této metody vynutí na projekt v `guidProjectID` načíst než metoda vrátí.  
  
> [!NOTE]
>  . Ve výchozím nastavení pouze projekty, které mají vyžádání načíst a pozadí zatížení priority jsou načtena, ale pokud <xref:Microsoft.VisualStudio.Shell.Interop.__VSBSLFLAGS> příznak, je předaná metodě, bude možné načíst všechny projekty, s výjimkou těch, které jsou označené explicitně načíst.