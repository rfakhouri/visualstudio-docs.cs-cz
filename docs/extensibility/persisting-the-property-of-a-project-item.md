---
title: "Uložením vlastnosti položky projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties, adding to a project item
- project items, adding properties
ms.assetid: d7a0f2b0-d427-4d49-9536-54edfb37c0f3
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e732821cf1ea14497038a65d49f2a10ce22c28a5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="persisting-the-property-of-a-project-item"></a>Uložením vlastnosti položky projektu
Chcete zachovat vlastnosti, které přidáte do projektu položkou, například autora zdrojového souboru. Můžete k tomu uložením vlastnost v souboru projektu.  
  
 Prvním krokem k zachování vlastnost v souboru projektu je použít k získání hierarchii projektu jako <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> rozhraní. Toto rozhraní můžete získat pomocí automatizace nebo pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>. Po získání rozhraní, můžete určit, která položka projektu je momentálně zvolen. Až budete mít ID položky projektu, můžete použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> přidat vlastnost.  
  
 V následujících postupech zachovat vlastnost VsPkg.cs `Author` s hodnotou `Tom` v souboru projektu.  
  
### <a name="to-obtain-the-project-hierarchy-with-the-dte-object"></a>K získání hierarchii projektu s objektem DTE  
  
1.  Přidejte následující kód do vaší VSPackage:  
  
    ```csharp  
    EnvDTE.DTE dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
    EnvDTE.Project project = dte.Solution.Projects.Item(1);  
  
    string uniqueName = project.UniqueName;  
    IVsSolution solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
    IVsHierarchy hierarchy;  
    solution.GetProjectOfUniqueName(uniqueName, out hierarchy);  
    ```  
  
### <a name="to-persist-the-project-item-property-with-the-dte-object"></a>Chcete-li zachovat vlastnosti položky projektu s objektem DTE  
  
1.  Přidejte následující kód do kód v metodě v předchozím postupu:  
  
    ```csharp  
    IVsBuildPropertyStorage buildPropertyStorage =   
        hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        uint itemId;  
        string fullPath = (string)project.ProjectItems.Item(  
            "VsPkg.cs").Properties.Item("FullPath").Value;  
        hierarchy.ParseCanonicalName(fullPath, out itemId);  
        buildPropertyStorage.SetItemAttribute(itemId, "Author", "Tom");  
    }  
    ```  
  
### <a name="to-obtain-the-project-hierarchy-using-ivsmonitorselection"></a>Získání projektu hierarchii pomocí IVsMonitorSelection  
  
1.  Přidejte následující kód do vaší VSPackage:  
  
    ```csharp  
    IVsHierarchy hierarchy = null;  
    IntPtr hierarchyPtr = IntPtr.Zero;  
    IntPtr selectionContainer = IntPtr.Zero;  
    uint itemid;  
  
    // Retrieve shell interface in order to get current selection  
    IVsMonitorSelection monitorSelection =     Package.GetGlobalService(typeof(SVsShellMonitorSelection)) as     IVsMonitorSelection;  
    if (monitorSelection == null)  
        throw new InvalidOperationException();  
  
    try  
    {  
        // Get the current project hierarchy, project item, and selection container for the current selection  
        // If the selection spans multiple hierachies, hierarchyPtr is Zero  
        IVsMultiItemSelect multiItemSelect = null;  
        ErrorHandler.ThrowOnFailure(  
            monitorSelection.GetCurrentSelection(  
                out hierarchyPtr, out itemid,   
                out multiItemSelect, out selectionContainer));  
  
        // We only care if there is only one node selected in the tree  
        if (!(itemid == VSConstants.VSITEMID_NIL ||   
            hierarchyPtr == IntPtr.Zero ||  
            multiItemSelect != null ||  
            itemid == VSConstants.VSITEMID_SELECTION))  
        {  
            hierarchy = Marshal.GetObjectForIUnknown(hierarchyPtr)  
                as IVsHierarchy;  
        }  
    }  
    finally  
    {  
        if (hierarchyPtr != IntPtr.Zero)  
            Marshal.Release(hierarchyPtr);  
        if (selectionContainer != IntPtr.Zero)  
            Marshal.Release(selectionContainer);  
    }  
    ```  
  
2.  
  
### <a name="to-persist-the-selected-project-item-property-given-the-project-hierarchy"></a>Udržení vlastnost položky vybrané projektu zadána hierarchii projektu  
  
1.  Přidejte následující kód do kód v metodě v předchozím postupu:  
  
    ```  
    IVsBuildPropertyStorage buildPropertyStorage =   
        hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        buildPropertyStorage.SetItemAttribute(itemId, "Author", "Tom");  
    }  
    ```  
  
### <a name="to-verify-that-the-property-is-persisted"></a>Chcete-li ověřit, že je vlastnost trvalá  
  
1.  Spustit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a poté otevřete nebo vytvořte řešení.  
  
2.  Vyberte projekt položky VsPkg.cs v **Průzkumníku řešení**.  
  
3.  Použít zarážku nebo jinak určit, zda je vaše VSPackage načteny a že SetItemAttribute běží.  
  
    > [!NOTE]
    >  Můžete autoload VSPackage v kontextu uživatelského rozhraní <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionExists>. Další informace najdete v tématu [načítání VSPackages](../extensibility/loading-vspackages.md).  
  
4.  Zavřít [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a pak otevřete soubor projektu v poznámkovém bloku. Měli byste vidět \<Autor > značku s hodnotou tní, následujícím způsobem:  
  
    ```  
    <Compile Include="VsPkg.cs">  
        <Author>Tom</Author>  
    </Compile>  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Vlastní nástroje](../extensibility/internals/custom-tools.md)