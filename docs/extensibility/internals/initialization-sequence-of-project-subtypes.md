---
title: Inicializační sekvence podtypů projektů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project subtypes, initialization sequence
ms.assetid: f657f8c3-5e68-4308-9971-e81e3099ba29
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a0e42f80485aab478e3739aedb42130699a963ac
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62909689"
---
# <a name="initialization-sequence-of-project-subtypes"></a>Inicializační sekvence podtypů projektů
Prostředí vytvoří projekt zavoláním implementace objektu factory základního projektu z <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>. Konstrukce podtyp projektu začne, když prostředí určuje, zda seznam identifikátor GUID typu projektu pro příponu souboru projektu není prázdný. Přípona souboru projektu a projekt GUID určete, jestli má projekt [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] nebo [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] typ projektu. Například rozšíření .vbproj a {F184B08F-C81C-45F6-A57F-5ABD9991F28F} identifikovat [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] projektu.

## <a name="environments-initialization-of-project-subtypes"></a>Inicializace prostředí podtypů projektů
 Následující postup podrobně popisuje pořadí inicializace pro projekt systému agregované podle více podtypů projektů.

1. Prostředí volá základní projekt <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>, a zatímco projektu analyzuje svůj soubor projektu zjistí, že typ agregace projektu seznamu identifikátorů GUID není `null`. Projekt navrátí přímé vytváření svůj projekt.

2. Volání projektu `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.SVsCreateAggregateProject> služby k vytvoření podtyp projektu pomocí prostředí provádění <xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> metody. V rámci této metody prostředí volá rekurzivní funkce do vaší implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.SetInnerProject%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.InitializeForOuter%2A> metod během jeho je procházení seznamu projektu zadejte identifikátory GUID, počínaje podtyp nejkrajnější projektu.

     Následující části najdete postup inicializace.

    1. Prostředí provádění <xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> volání metod `HrCreateInnerProj` metody s deklarací následující funkce:

         \<CodeContentPlaceHolder>0</CodeContentPlaceHolder>

         Když tato funkce je volána poprvé, to znamená, pro podtyp projektu nejkrajnější parametry `pOuter` a `pOwner` předaný jako `null` a funkce nastaví podtyp projektu nejkrajnější `IUnknown` k `pOuter`.

    2. Vedle prostředí volá `HrCreateInnerProj` funkce druhého typu projektu GUID v seznamu. Tento identifikátor GUID odpovídá druhý vnitřní projektu podtyp krokování směrem k základního projektu postupně agregace.

    3. `pOuter` Teď přejdete `IUnknown` podtypu nejkrajnější projektu a `HrCreateInnerProj` volá vaši implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A> za nímž následuje volání implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.SetInnerProject%2A>. V <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A> metodu předáním řízení `IUnknown` podtypu nejkrajnější projektu `pOuter`. Vlastněné projektu (vnitřní projektu podtyp) potřebuje k vytvoření jeho agregační projektu objekt. V <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.SetInnerProject%2A> můžete předat ukazatel na implementaci metody `IUnknown` vnitřní projektu, který je agregaci. Tyto dvě metody vytvoření agregace objektu, a vaše implementace muset postupovat podle modelu COM agregace pravidla pro zajištění, že podtyp projektu nekončí nahoru obsahující počet odkazů na sebe sama.

    4. `HrCreateInnerProj` volá vaši implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A>. V této metodě podtyp projektu nemá svoji inicializaci. Můžete například zaregistrovat řešení události v <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.InitializeForOuter%2A>.

    5. `HrCreateInnerProj` rekurzivně je volána, dokud nebude dosaženo poslední GUID (základní projekt) v seznamu. Pro každou z těchto volání kroky, až d, c se opakují. `pOuter` odkazuje na podtyp projektu nejkrajnější `IUnknown` na jednotlivých úrovních agregace.

## <a name="example"></a>Příklad

V následujícím příkladu je podrobně popsán programový proces v reprezentaci přibližné <xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> metody, jak je implementované prostředí. Kód je uvedené jenom jako příklad; není určena ke kompilaci, a všechny kontroly chyb byl odebrán nejasnostem.

```cpp
HRESULT CreateAggregateProject
(
    LPCOLESTR lpstrGuids,
    LPCOLESTR pszFilename,
    LPCOLESTR pszLocation,
    LPCOLESTR pszName,
    VSCREATEPROJFLAGS grfCreateFlags,
    REFIID iidProject,
    void **ppvProject)
{
    HRESULT hr = NOERROR;
    CComPtr<IUnknown> srpunkProj;
    CComPtr<IVsAggregatableProject> srpAggProject;
    CComBSTR bstrGuids = lpstrGuids;
    BOOL fCanceled = FALSE;
    *ppvProject = NULL;

    HrCreateInnerProj(
         bstrGuids, NULL, NULL, pszFilename, pszLocation,
         pszName, grfCreateFlags, &srpunkProj, &fCanceled);
    srpunkProj->QueryInterface(
        IID_IVsAggregatableProject, (void **)&srpAggProject));
    srpAggProject->OnAggregationComplete();
    srpunkProj->QueryInterface(iidProject, ppvProject);
}

HRESULT HrCreateInnerProj
(
    WCHAR *pwszGuids,
    IUnknown *pOuter,
    IVsAggregatableProject *pOwner,
    LPCOLESTR pszFilename,
    LPCOLESTR pszLocation,
    LPCOLESTR pszName,
    VSCREATEPROJFLAGS grfCreateFlags,
    IUnknown **ppInner,
    BOOL *pfCanceled
)
{
    HRESULT hr = NOERROR;
    CComPtr<IUnknown> srpInner;
    CComPtr<IVsAggregatableProject> srpAggInner;
    CComPtr<IVsProjectFactory> srpProjectFactory;
    CComPtr<IVsAggregatableProjectFactory> srpAggPF;
    GUID guid = GUID_NULL;
    WCHAR *pwszNextGuids = wcschr(pwszGuids, L';');
    WCHAR wszText[_MAX_PATH+150] = L"";

    if (pwszNextGuids)
    {
        *pwszNextGuids++ = 0;
    }

    CLSIDFromString(pwszGuids, &guid);
    GetProjectTypeMgr()->HrGetProjectFactoryOfGuid(
        guid, &srpProjectFactory);
    srpProjectFactory->QueryInterface(
        IID_IVsAggregatableProjectFactory,
        (void **)&srpAggPF);
    srpAggPF->PreCreateForOuter(pOuter, &srpInner);
    srpInner->QueryInterface(
        IID_IVsAggregatableProject, (void **)&srpAggInner);

    if (pOwner)
    {
        IfFailGo(pOwner->SetInnerProject(srpInner));
    }

    if (pwszNextGuids)
    {
        CComPtr<IUnknown> srpNextInner;
        HrCreateInnerProj(
            pwszNextGuids, pOuter ? pOuter : srpInner,
            srpAggInner, pszFilename, pszLocation, pszName,
            grfCreateFlags, &srpNextInner, pfCanceled);
    }

    return srpAggInner->InitializeForOuter(
        pszFilename, pszLocation, pszName, grfCreateFlags,
        IID_IUnknown, (void **)ppInner, pfCanceled);
}
```

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.Shell.Flavor>
- [Podtypy projektů](../../extensibility/internals/project-subtypes.md)