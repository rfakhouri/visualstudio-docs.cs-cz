---
title: Updatemanifestforbrowserapplication – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3935b03bfc680e0422e6336d46677ad1830ce7ff
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="updatemanifestforbrowserapplication-task"></a>UpdateManifestForBrowserApplication – úloha
<xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication> Spuštění úlohy Přidat  **\<hostinbrowser – / >** element manifest aplikace (*projectname*. exe.manifest) při [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)] sestavení projektu.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ApplicationManifest`|Požadované **[ITaskItem]** parametr.<br /><br /> Určuje cestu a název souboru manifestu aplikace, který chcete přidat `<hostInBrowser />` element.|  
|`HostInBrowser`|Požadované **Boolean** parametr.<br /><br /> Určuje, zda chcete upravit manifest aplikace zahrnout  **\<hostinbrowser – / >** element. Pokud **true**, nový `<` **hostinbrowser – / >** element je součástí  **\<entryPoint / >** element. Všimněte si, že element zahrnutí je kumulativní: Pokud  **\<hostinbrowser – / >** element již existuje, není odebrat nebo přepsat. Místo toho další  **\<hostinbrowser – / >** element je vytvořen. Pokud **false**, manifest aplikace se nemění.|  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[TLA2#tla_xbap#plural](../msbuild/includes/tla2sharptla_xbapsharpplural_md.md)] spustit pomocí [!INCLUDE[TLA#tla_clickonce](../msbuild/includes/tlasharptla_clickonce_md.md)] nasazení a proto musí pomocí publikování s podpora manifesty nasazení a aplikací. [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)] používá [GenerateApplicationManifest](http://msdn2.microsoft.com/library/6wc2ccdc.aspx) úloh vygenerovat manifest aplikace.  
  
 Potom pro konfiguraci aplikace pro hostování v prohlížeči na další prvek  **\<hostinbrowser – / >** musí být přidaný do manifestu aplikace, jak je vidět v následujícím příkladu:  
  
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
  
 <xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication> Při spuštění úlohy [!INCLUDE[TLA2#tla_xbap](../msbuild/includes/tla2sharptla_xbap_md.md)] sestavení projektu chcete-li přidat `<hostInBrowser />` elementu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak zajistit, aby `<hostInBrowser />` element je zahrnutá v souboru manifestu aplikace.  
  
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
  
## <a name="see-also"></a>Viz také  
 [WPF MSBuild – Reference](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Vytvoření aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)   
 [Přehled aplikací Prohlížeče WPF XAML](/dotnet/framework/wpf/app-development/wpf-xaml-browser-applications-overview)