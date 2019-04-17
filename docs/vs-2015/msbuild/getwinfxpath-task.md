---
title: Getwinfxpath – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- getting the directory of the current .NET Framework runtime [WPF MSBuild]
- GetWinFXPath task [WPF MSBuild], parameters
- GetWinFXPath task [WPF MSBuild]
- obtaining the path to the current .NET Framework runtime [WPF MSBuild]
ms.assetid: b1dfb467-f3d3-47f3-83ef-af7b0e33a772
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 846eb1ca1c63ee8dad88d31bbc574ef6d71efc4b
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59657742"
---
# <a name="getwinfxpath-task"></a>GetWinFXPath – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:Microsoft.Build.Tasks.Windows.GetWinFXPath> Vrácený obsah úkolů adresář aktuálního [!INCLUDE[TLA#tla_winfx](../includes/tlasharptla-winfx-md.md)] modulu runtime.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`WinFXPath`|Volitelné **řetězec** výstupní parametr.<br /><br /> Určuje skutečné cesty k [!INCLUDE[TLA2#tla_winfx](../includes/tla2sharptla-winfx-md.md)] modulu runtime.|  
|`WinFXNativePath`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje cestu k nativní [!INCLUDE[TLA2#tla_titlewinfx](../includes/tla2sharptla-titlewinfx-md.md)] modulu runtime.|  
|`WinFXWowPath`|Vyžaduje **řetězec** parametru.<br /><br /> Určuje cestu k [!INCLUDE[TLA#tla_winfx](../includes/tlasharptla-winfx-md.md)] sestavení v 32bitovém základě **Windows na Windows** modulu v 64bitových systémech.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud <xref:Microsoft.Build.Tasks.Windows.GetWinFXPath> 64bitový procesor, je spuštěn úkol **WinFXPath** parametr je nastaven na cestu, která je uložena v **WinFXWowPath** parametr; v opačném případě **WinFXPath**  parametr je nastaven na cestu, která je uložena v **WinFXNativePath** parametru.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití **getwinfxpath –** úloh ke zjištění nativní cestou k [!INCLUDE[TLA2#tla_titlewinfx](../includes/tla2sharptla-titlewinfx-md.md)] modulu runtime.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.GetWinFXPath"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="GetWinFXPathTask">  
    <GetWinFXPath  
      WinFXNativePath="c:\WinFXNative"   
      WinFXWowPath="c:\WinFXWowNative" />  
  </Target>  
  <Import Project="$(MSBuildBinPath)\Microsoft.WinFX.targets" />  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Sestavení aplikace WPF (WPF)](http://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)
