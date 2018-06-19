---
title: Řešení (. Soubor SLN –) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- sln files, VSPackages
- solutions, .sln files
- .sln files, VSPackages
ms.assetid: 7d7ef539-2e4b-4637-b853-8ec7626609df
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 73d6f7fb83e9420f59122135761ce44ea641fe57
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133401"
---
# <a name="solution-sln-file"></a>Řešení (. Soubor SLN –)
Řešení je struktura pro uspořádání projekty v sadě Visual Studio. Řešení udržuje informace o stavu pro projekty v .sln (založený na textu, sdílený) a soubory .suo (možnosti řešení binární, specifický pro uživatele). Další informace o soubory .suo najdete v tématu [uživatelské možnosti řešení (. Suo) soubor](../../extensibility/internals/solution-user-options-dot-suo-file.md).  
  
 Pokud vaše VSPackage je načtena v důsledku odkazuje ve soubor .sln, zavolá prostředí <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> ke čtení v soubor .sln.  
  
 Soubor .sln obsahuje textové informace, které používá prostředí můžete najít a načíst parametry název hodnota pro trvalá data a projekt VSPackages odkazuje. Když uživatel otevře řešení, prostředí procházení `preSolution`, `Project`, a `postSolution` informace v souboru .sln načtení tohoto řešení pro projekty v řešení a údaje trvalé připojené k řešení.  
  
 Každý projekt soubor obsahuje další informace o čtení prostředí k naplnění hierarchie s položky tohoto projektu. Řídí trvalosti dat hierarchie projektu. data není normálně uložené v souboru .sln, i když může záměrně zapsat informace o projektu soubor .sln, pokud se rozhodnete tak učinit. Další informace týkající se trvalosti najdete v tématu [projektu trvalost](../../extensibility/internals/project-persistence.md) a [otevírání a ukládání položky projektu](../../extensibility/internals/opening-and-saving-project-items.md).  
  
## <a name="solution-file-contents"></a>Obsah souboru řešení  
 Soubor .sln se skládá z několika oddílů, jak je znázorněno v následujícím kódu.  
  
```  
Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1", "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}"  
EndProject  
Global  
  GlobalSection(SolutionNotes) = postSolution  
  EndGlobalSection  
  GlobalSection(SolutionConfiguration) = preSolution  
       ConfigName.0 = Debug  
       ConfigName.1 = Release  
  EndGlobalSection  
  GlobalSection(ProjectDependencies) = postSolution  
  EndGlobalSection  
  GlobalSection(ProjectConfiguration) = postSolution  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.ActiveCfg = Debug|x86  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.Build.0 = Debug|x86  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.ActiveCfg = Release|x86  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.Build.0 = Release|x86  
  EndGlobalSection  
  GlobalSection(ExtensibilityGlobals) = postSolution  
  EndGlobalSection  
  GlobalSection(ExtensibilityAddIns) = postSolution  
  EndGlobalSection  
EndGlobal  
```  
  
 Načtení řešení, prostředí provádí následující pořadí úloh.  
  
1.  Prostředí čte části globální soubor .sln a zpracovává všechny části označené `preSolution`. V takovém případě je jeden takový příkaz:  
  
    ```  
    GlobalSection(SolutionConfiguration) = preSolution  
         ConfigName.0 = Debug  
         ConfigName.1 = Release  
    ```  
  
     Při čtení prostředí `GlobalSection('name')` štítku mapuje název na VSPackage pomocí klíče registru. Název klíče by měla existovat v klíči registru [HKLM\\< kořenový adresář aplikace ID registru\>\SolutionPersistence\AggregateGUIDs]. Klíče výchozí hodnota je v balíčku GUID (REG_SZ) VSPackage, který napsal položky.  
  
2.  Prostředí načte VSPackage volání `QueryInterface` na VSPackage pro <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> rozhraní a volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> metoda s daty v části, VSPackage můžete ukládat data. V prostředí se tento proces opakuje pro každou `preSolution` části.  
  
3.  Prostředí iteruje bloky trvalost projektu. V takovém případě je jeden projekt.  
  
    ```  
    Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1",  
    "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}"  
    EndProject  
    ```  
  
     Tento příkaz obsahuje jedinečný identifikátor GUID projekt a projekt typu GUID. Tyto informace slouží v prostředí se najít soubor projektu nebo soubory, které patří k řešení a VSPackage vyžadované pro každý projekt. Projekt je předán GUID <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> načíst konkrétní VSPackage související s projekt, pak načtení projektu pomocí VSPackage. V takovém případě je VSPackage, který je načten pro tento projekt jazyka Visual Basic.  
  
     Každý projekt, můžete zachovat ID instance jedinečný projektu tak, aby k němu podle potřeby další projekty v řešení. V ideálním případě pokud řešení a projekty jsou ve správě zdrojového kódu, cesta k projektu by měla být relativní k cestě k řešení. Při prvním načtení řešení, soubory projektu nelze na počítači uživatele. Tak, že soubor projektu, které jsou uloženy na serveru vůči soubor řešení, je poměrně jednoduché pro projekt souboru nalezen a zkopírují se na počítači uživatele. Potom zkopíruje a načte zbytek soubory potřebné pro projekt.  
  
4.  Podle informací obsažených v části projektu soubor .sln, prostředí načte každý soubor projektu. Pro naplnění hierarchii projektu a načítání všechny vnořené projekty pak zodpovídá samotného projektu.  
  
5.  Po zpracování všech oddílů soubor .sln řešení se zobrazí v Průzkumníku řešení a je připravený pro úpravu uživatelem.  
  
 Pokud se nepodaří načíst, všechny VSPackage, který implementuje projektu v řešení <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.OnProjectLoadFailure%2A> metoda je volána a všechny ostatní projekty v řešení je zadána možnost Ignorovat změny, které jste zadali během načítání. Pokud dojde k chybám analýzy, co nejvíce informací se zachová, i s soubory řešení a prostředí zobrazí dialogové okno s upozorněním, že je poškozená řešení.  
  
 Když je řešení uložené nebo zavřená, <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.QuerySaveSolutionProps%2A> metoda je volána a předána do hierarchie, které chcete zobrazit, pokud byly provedeny změny na řešení, které je nutné zadat do souboru .sln. Hodnota null, předané do `QuerySaveSolutionProps` v <xref:Microsoft.VisualStudio.Shell.Interop.VSQUERYSAVESLNPROPS>, označuje, že je byly trvalé informace pro řešení. Pokud hodnota není null, je trvalé informace pro konkrétní projekt, dáno má ukazatel na <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> rozhraní.  
  
 Pokud nejsou informace uložit, <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> rozhraní je volán s odkazy <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.SaveSolutionProps%2A> metoda. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> Metoda je volána poté prostředí tak, aby načíst z dvojice název hodnota `IPropertyBag` rozhraní a zapsat informace o soubor .sln.  
  
 `SaveSolutionProps` a `WriteSolutionProps` objekty se nazývají rekurzivně prostředí k načtení informací z Uložit `IPropertyBag` rozhraní, dokud všechny změny byly zadány do soubor .sln. Tímto způsobem můžete zajistěte, aby se zachovat informace pomocí řešení a k dispozici při příštím otevření řešení.  
  
 Každý načíst VSPackage je výčet a zjistěte, zda má položky, které lze uložit do souboru .sln. Je pouze v době zatížení, který je dotazován klíče registru. Prostředí ví o všech balíčků načíst, protože se v paměti v době, kdy je uložena řešení.  
  
 Jenom soubor .sln obsahuje položky v `preSolution` a `postSolution` oddíly. Nejsou žádné podobné části v souboru .suo, protože řešení musí tyto informace načíst správně. Soubor .suo obsahuje možnosti specifické pro uživatele, jako jsou privátní poznámky, které nejsou určeny k sdílené nebo umístěny ve správě zdrojového kódu.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>   
 [Možnosti uživatele řešení (. Soubor suo)](../../extensibility/internals/solution-user-options-dot-suo-file.md)   
 [Řešení](../../extensibility/internals/solutions.md)