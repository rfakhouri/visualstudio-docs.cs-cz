---
title: Vystavení objektů projekt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project objects, exposing
- extensibility, project objects
ms.assetid: 5bb24967-434a-4ef4-87a0-2f3250c9e22d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4eaa2a5e8c5c153698069084b9f0cfe406cad7db
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130450"
---
# <a name="exposing-project-objects"></a>Vystavení objektů projektu
Typy vlastních projektů zajistí objekty automatizace, aby bylo možné povolit přístup k projektu pomocí rozhraní automatizace. Každý typ projektu se očekává poskytování standardní <xref:EnvDTE.Project> automatizace objektu, který je přístupný z <xref:EnvDTE.Solution>, který obsahuje kolekce všechny projekty, které jsou otevřeny v integrovaném vývojovém prostředí. Každá položka v projektu musí být vystavené <xref:EnvDTE.ProjectItem> objekt s `Project.ProjectItems`. Kromě těchto objektů standardní automatizace můžete zvolit projekty nabízejí objekty automatizace specifické pro projekt.  
  
 Můžete vytvořit vlastní automatizace na kořenové úrovni objekty, které dostanete pozdní vazbou z kořenové DTE objekt pomocí `DTE.<customeObjectName>` nebo `DTE.GetObject("<customObjectName>")`. Visual C++ například vytvoří kolekci projektu konkrétní projektu C++ s názvem "Umístěním", který můžete přistupovat pomocí DTE. Umístěním nebo DTE. GetObject("VCProjects"). Můžete také vytvořit Project.Object, které je jedinečné pro typ projektu, Project.CodeModel, který může být dotázán na jeho většinou odvozených objekt, ProjectItem, který zveřejňuje ProjectItem.Object a ProjectItem.FileCodeModel.  
  
 Je běžné konvence pro projekty vystavit kolekci projektů vlastní, specifické pro projekt. Například [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] vytvoří kolekci konkrétní projektu C++, která pak můžete přistupovat pomocí `DTE.VCProjects` nebo `DTE.GetObject("VCProjects")`. Můžete také vytvořit `Project.Object`, což je jedinečný pro typ projektu `Project.CodeModel`, který může být dotazován pro objekt jeho většinou odvozených `ProjectItem`, která zpřístupňuje `ProjectItem.Object`a `ProjectItem.FileCodeModel`.  
  
### <a name="to-contribute-a-vspackage-specific-object-for-a-project"></a>Přispívání objekt VSPackage specifické pro projekt  
  
1.  Přidejte do souboru .pkgdef vaše VSPackage odpovídající klíče.  
  
     Tady jsou například .pkgdef nastavení projektu jazyka C++:  
  
    ```  
    [$RootKey$\Packages\{F1C25864-3097-11D2-A5C5-00C04F7968B4}\Automation]  
    "VCProjects"=""  
    [$RootKey$\Packages\{F1C25864-3097-11D2-A5C5-00C04F7968B4}\AutomationEvents]  
    "VCProjectEngineEventsObject"=""  
    ```  
  
2.  Implementace kód <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> metoda jako v následujícím příkladu.  
  
    ```cpp  
    STDMETHODIMP CVsPackage::GetAutomationObject(  
    /* [in]  */ LPCOLESTR       pszPropName,   
    /* [out] */ IDispatch **    ppIDispatch)  
    {  
    ExpectedPtrRet(pszPropName);  
    ExpectedPtrRet(ppIDispatch);  
    *ppIDispatch = NULL;  
  
        if (m_fZombie)  
            return E_UNEXPECTED;  
  
        if (_wcsicmp(pszPropName, g_wszAutomationProjects) == 0)  
        {  
            return GetAutomationProjects(ppIDispatch);  
        }  
        else if (_wcsicmp(pszPropName, g_wszAutomationProjectsEvents) == 0)  
        {  
            return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
        }  
        else if (_wcsicmp(pszPropName, g_wszAutomationProjectItemsEvents) == 0)  
        {  
            return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
        }  
        return E_INVALIDARG;  
    }   
    ```  
  
     V kódu `g_wszAutomationProjects` je název kolekci projektu. `GetAutomationProjects` Metoda vytvoří objekt, který implementuje `Projects` rozhraní a vrátí `IDispatch` ukazatel na objekt volání, jak je uvedené v následujícím příkladu kódu.  
  
    ```cpp  
    HRESULT CVsPackage::GetAutomationProjects(/* [out] */ IDispatch ** ppIDispatch)  
    {  
        ExpectedPtrRet(ppIDispatch);  
        *ppIDispatch = NULL;  
  
        if (!m_srpAutomationProjects)  
        {  
            HRESULT hr = CACProjects::CreateInstance(&m_srpAutomationProjects);  
            IfFailRet(hr);  
            ExpectedExprRet(m_srpAutomationProjects != NULL);  
        }  
        return m_srpAutomationProjects.CopyTo(ppIDispatch);  
    }  
    ```  
  
     Měli byste vybrat jedinečný název objektu automatizace. Název je v konfliktu se nepředvídatelným a kolizí způsobit konfliktní název objektu nahodile vyvolání Pokud více typů projektu používají stejný název. By měla obsahovat název vaší společnosti nebo některé jedinečné aspekt jeho název produktu, název objektu automatizace.  
  
     Vlastní `Projects` objektu kolekce je užitečný vstupním bodem pro zbývající část modelu automatizace projektu. Objekt vašeho projektu je také přístupné z <xref:EnvDTE.Solution> projektu kolekce. Po vytvoření odpovídající kód a registru položky, které poskytují spotřebitelé s `Projects` kolekci objektů, implementaci musíte zadat zbývající standardní objekty pro projekt modelu. Další informace najdete v tématu [projekt modelování](../../extensibility/internals/project-modeling.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>