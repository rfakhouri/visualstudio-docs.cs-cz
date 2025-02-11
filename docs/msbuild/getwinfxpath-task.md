---
title: Getwinfxpath – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c95e5ad882d7021b597d7ba0ad8c38177f4a5136
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996343"
---
# <a name="getwinfxpath-task"></a>Getwinfxpath – úloha
<xref:Microsoft.Build.Tasks.Windows.GetWinFXPath> Vrácený obsah úkolů adresář aktuálního [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)] modulu runtime.

## <a name="task-parameters"></a>Parametry úlohy

| Parametr | Popis |
|-------------------| - |
| `WinFXPath` | Volitelné **řetězec** výstupní parametr.<br /><br /> Určuje skutečné cesty k [!INCLUDE[TLA2#tla_winfx](../msbuild/includes/tla2sharptla_winfx_md.md)] modulu runtime. |
| `WinFXNativePath` | Vyžaduje **řetězec** parametru.<br /><br /> Určuje cestu k nativní [!INCLUDE[TLA2#tla_titlewinfx](../msbuild/includes/tla2sharptla_titlewinfx_md.md)] modulu runtime. |
| `WinFXWowPath` | Vyžaduje **řetězec** parametru.<br /><br /> Určuje cestu k [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)] sestavení v 32bitovém základě **Windows na Windows** modulu v 64bitových systémech. |

## <a name="remarks"></a>Poznámky
 Pokud <xref:Microsoft.Build.Tasks.Windows.GetWinFXPath> 64bitový procesor, je spuštěn úkol **WinFXPath** parametr je nastaven na cestu, která je uložena v **WinFXWowPath** parametr; v opačném případě **WinFXPath**  parametr je nastaven na cestu, která je uložena v **WinFXNativePath** parametru.

## <a name="example"></a>Příklad
 Následující příklad ukazuje způsob použití **getwinfxpath –** úloh ke zjištění nativní cestou k [!INCLUDE[TLA2#tla_titlewinfx](../msbuild/includes/tla2sharptla_titlewinfx_md.md)] modulu runtime.

```xml
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

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)
- [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)
- [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
- [Sestavení aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)
