---
title: Updatemanifestforbrowserapplication – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UpdateManifestForBrowserApplication task [WPF MSBuild]
- adding the <hostInBrowser /> element to the application manifest [WPF MSBuild]
- building XBAP projects [WPF MSBuild]
- UpdateManifestForBrowserApplication task [WPF MSBuild], parameters
ms.assetid: 653339f7-654b-4d64-a26a-5c9f27036895
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f6a346ff1359494e62483a0d2b7954b405880511
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/19/2018
ms.locfileid: "39155474"
---
# <a name="updatemanifestforbrowserapplication-task"></a>Updatemanifestforbrowserapplication – úloha
<xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication> Spuštění úlohy Přidat  **\<hostInBrowser / >** element do manifestu aplikace (*\<projectname >. exe.manifest*) při [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)] Projekt se vytvořil.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ApplicationManifest`|Vyžaduje **[] ITaskItem** parametru.<br /><br /> Určuje cestu a název souboru manifestu aplikace, které chcete přidat `<hostInBrowser />` elementu.|  
|`HostInBrowser`|Vyžaduje **logická** parametru.<br /><br /> Určuje, jestli se má upravit manifest aplikace, které chcete zahrnout  **\<hostInBrowser / >** elementu. Pokud **true**, nový  **\<hostInBrowser / >** element je součástí  **\<vstupního bodu / >** elementu. Zahrnutí elementu je kumulativní: Pokud  **\<hostInBrowser / >** element už existuje, není odebrat nebo přepsat. Místo toho další  **\<hostInBrowser / >** vytvořit prvek. Pokud **false**, manifest aplikace se nezmění.|  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[TLA2#tla_xbap#plural](../msbuild/includes/tla2sharptla_xbapsharpplural_md.md)] spuštění pomocí [!INCLUDE[TLA#tla_clickonce](../msbuild/includes/tlasharptla_clickonce_md.md)] nasazení, takže musí být publikovány s podpůrnými manifesty nasazení a aplikace. [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)] používá [generateapplicationmanifest –](http://msdn2.microsoft.com/library/6wc2ccdc.aspx) úkolů ke generování manifestu aplikace.  
  
 Pak nakonfigurujte aplikaci zajistit také jejich hostování v prohlížeči, zobrazí se další  **\<hostInBrowser / >** elementu musí být přidán do manifestu aplikace, jak je znázorněno v následujícím příkladu:  
  
```xml  
<!--MyXBAPApplication.exe.manifest-->  
<?xml version="1.0" encoding="utf-8"?>  
<asmv1:assembly ... >  
    <asmv1:assemblyIdentity ... />  
    <application />  
    <entryPoint>  
      ...  
      <hostInBrowser xmlns="urn:schemas-microsoft-com:asm.v3" />  
    </entryPoint>  
  ...  
/>  
```  
  
 <xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication> Při spuštění úlohy [!INCLUDE[TLA2#tla_xbap](../msbuild/includes/tla2sharptla_xbap_md.md)] sestavení projektu, aby bylo možné přidat `<hostInBrowser />` elementu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak Ujistěte se, že `<hostInBrowser />` element je součástí souboru manifestu aplikace.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication"  
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="UpdateManifestForBrowserApplicationTask">  
    <UpdateManifestForBrowserApplication  
      ApplicationManifest="MyXBAPApplication.exe.manifest"  
      HostInBrowser="true" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Sestavení aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)   
 [Přehled aplikací prohlížeče WPF XAML](/dotnet/framework/wpf/app-development/wpf-xaml-browser-applications-overview)