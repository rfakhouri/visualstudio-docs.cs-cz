---
title: Vystavení události v sadě Visual Studio SDK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- events [Visual Studio], exposing
- automation [Visual Studio SDK], exposing events
ms.assetid: 70bbc258-c221-44f8-b0d7-94087d83b8fe
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 02ddcf0c2321f6f4c07170117c6474b993c340f4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132231"
---
# <a name="exposing-events-in-the-visual-studio-sdk"></a>Vystavení události v sadě Visual Studio SDK
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Umožňuje zdroje událostí s použitím automatizace. Doporučujeme vám, že je zdroj události pro projekty a položky projektu.  
  
 Události jsou načítána automatizace příjemců z <xref:EnvDTE.DTEClass.Events%2A> objekt nebo <xref:EnvDTE.DTEClass.GetObject%2A> ("EventObjectName"). Volání prostředí `IDispatch::Invoke` pomocí `DISPATCH_METHOD` nebo `DISPATCH_PROPERTYGET` příznaky vrátit událost.  
  
 Následující postup vysvětluje, jak jsou vráceny události specifické pro VSPackage.  
  
1.  Spustí se prostředí.  
  
2.  Načte všechny názvy hodnot v části klíče automatizace, AutomationEvents a AutomationProperties všechny VSPackages z registru a ukládá tyto názvy v tabulce.  
  
3.  Příjemce automatizace volá, v tomto příkladu `DTE.Events.AutomationProjectsEvents` nebo `DTE.Events.AutomationProjectItemsEvents`.  
  
4.  Prostředí parametr řetězec najde v tabulce a načte odpovídající VSPackage.  
  
5.  Volání prostředí <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> metody pomocí názvu předán ve volání; v tomto příkladu AutomationProjectsEvents nebo AutomationProjectItemsEvents.  
  
6.  Vytvoří kořenový objekt, který má metody, jako VSPackage `get_AutomationProjectsEvents` a `get_AutomationProjectItemEvents` a potom se vrátí IDispatch ukazatele na objekt.  
  
7.  Prostředí volá odpovídající metodu na základě názvu předaný do volání automatizace.  
  
8.  `get_` Metoda vytvoří další události na základě IDispatch objekt, který implementuje i `IConnectionPointContainer` rozhraní a `IConnectionPoint` rozhraní a vrátí IDispatchpointer k objektu.  
  
 Ke zveřejnění událost pomocí automatizace, musí reagovat na <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> a sledovat řetězce, které přidáte do registru. V ukázce základního projektu řetězce jsou "BscProjectsEvents" a "BscProjectItemsEvents".  
  
## <a name="registry-entries-from-the-basic-project-sample"></a>Položky registru od základního projektu vzorku  
 Tato část uvádí kde přidejte hodnoty pro události automatizace do registru.  
  
 [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Packages\\< PkgGUID\>\AutomationEvents]  
  
 "AutomationProjectEvents"="vrátí objekt AutomationProjectEvents"  
  
 "AutomationProjectItemEvents"="vrátí objekt AutomationProjectItemsEvents"  
  
|Název|Typ|Rozsah|Popis|  
|----------|----------|-----------|-----------------|  
|Výchozí (@)|REG_SZ|Nepoužitý|Nepoužívá se. Pole dat můžete použít pro dokumentaci.|  
|AutomationProjectsEvents|REG_SZ|Název události objektu.|Pouze název klíče je relevantní. Pole dat můžete použít pro dokumentaci.<br /><br /> Tento příklad pochází z ukázkové základní projektu.|  
|AutomationProjectItemEvents|REG_SZ|Název objektu událostí|Pouze název klíče je relevantní. Pole dat můžete použít pro dokumentaci.<br /><br /> Tento příklad pochází z ukázkové základní projektu.|  
  
 Když některé z vašich objektů událostí jsou požadoval příjemce automatizace, vytvořte kořenový objekt, který má metody pro událostí, které podporuje vaše VSPackage. Prostředí volá odpovídající `get_` metoda u tohoto objektu. Například pokud `DTE.Events.AutomationProjectsEvents` je volána, `get_AutomationProjectsEvents` je volána metoda na kořenový objekt.  
  
 ![Události projektu sady Visual Studio](../../extensibility/internals/media/projectevents.gif "ProjectEvents")  
Model automatizace pro události  
  
 Třída `CProjectEventsContainer` představuje zdrojového objektu pro BscProjectsEvents, zatímco `CProjectItemsEventsContainer` představuje zdrojového objektu pro BscProjectItemsEvents.  
  
 Ve většině případů musí vrátit nový objekt pro každý požadavek událost, protože většinu objektů událostí trvat objekt filtru. Pokud jste fire událost, zkontrolujte tento filtr k ověření, že je volána obslužná rutina události.  
  
 AutomationEvents.h a AutomationEvents.cpp obsahují deklarace a implementaci třídy v následující tabulce.  
  
|Třída|Popis|  
|-----------|-----------------|  
|`CAutomationEvents`|Implementuje objekt kořenové událost načítají `DTE.Events` objektu.|  
|`CProjectsEventsContainer` A `CProjectItemsEventsContainer`|Implementace objektů zdroje událostí, které budou spuštěny odpovídající události.|  
  
 Následující příklad kódu ukazuje, jak reagovat na žádost o objekt události.  
  
```cpp  
STDMETHODIMP CVsPackage::GetAutomationObject(  
    /* [in]  */ LPCOLESTR       pszPropName,   
    /* [out] */ IDispatch **    ppIDispatch)  
{  
    ExpectedPtrRet(ppIDispatch);  
    *ppIDispatch = NULL;  
  
    if (_wcsicmp(pszPropName, g_wszAutomationProjects) == 0)   
        //Is the requested name our Projects object?  
    {  
        return GetAutomationProjects(ppIDispatch);  
        // Gets our Projects object.  
    }  
    else if (_wcsicmp(pszPropName, g_wszAutomationProjectsEvents) == 0)  
        //Is the requested name our ProjectsEvents object?  
    {  
        return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
          // Gets our ProjectEvents object.  
    }  
    else if (_wcsicmp(pszPropName, g_wszAutomationProjectItemsEvents) == 0)  //Is the requested name our ProjectsItemsEvents object?  
    {  
        return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
          // Gets our ProjectItemsEvents object.  
    }  
    return E_INVALIDARG;  
}  
```  
  
 Ve výše, kódu `g_wszAutomationProjects` je název kolekci projektu ("FigProjects"), `g_wszAutomationProjectsEvents` ("FigProjectsEvents") a `g_wszAutomationProjectItemsEvents` ("FigProjectItemEvents") jsou názvy projektu události a události, které pocházejí z položek projektu vaší Implementace VSPackage.  
  
 Objektů událostí se načítají ze stejného centrální umístění, `DTE.Events` objektu. Tímto způsobem, všechny objekty událostí jsou seskupeny dohromady, aby koncový uživatel nebude muset procházet celý objekt modelu k vyhledání konkrétní události. To také umožňuje poskytovat konkrétní objekty VSPackage, místo aby můžete implementovat vlastní kód pro systémové události. Ale pro koncového uživatele, kteří musí najít událost pro vaše `ProjectItem` rozhraní, není okamžitě jasné, ze kterých je tento objekt události načíst.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>   
 [Ukázky VSSDK](http://aka.ms/vs2015sdksamples)