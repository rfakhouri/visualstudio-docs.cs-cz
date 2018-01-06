---
title: "AspNetCompiler – úloha pomocí předkompilovat aplikace ASP.NET | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#AspNetCompiler
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, AspNetCompiler task
- AspNetCompiler task [MSBuild]
ms.assetid: f811c019-a67b-4d54-82e6-e29549496f6e
caps.latest.revision: "11"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: aspnet
ms.openlocfilehash: 3299efa1675e4e9d173379fbb00f09c1d8ece414
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="aspnetcompiler-task"></a>AspNetCompiler – úloha
`AspNetCompiler` Úloh zabalí aspnet_compiler.exe, nástroj předkompilovat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `AspNetCompiler` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AllowPartiallyTrustedCallers`|Volitelné `Boolean` parametr.<br /><br /> Pokud tento parametr je `true`,, sestavení silným názvem bude povolit částečně důvěryhodné volající.|  
|`Clean`|Volitelné `Boolean` parametr<br /><br /> Pokud tento parametr je `true`, předkompilované aplikace budou vytvořeny vyčistit. Všechny dříve kompilované komponenty bude zopakovat. Výchozí hodnota je `false`. Tento parametr odpovídá **- c** přepínač na aspnet_compiler.exe.|  
|`Debug`|Volitelné `Boolean` parametr.<br /><br /> Pokud tento parametr je `true`, informace o ladění (. Soubor PDB) jsou vydávány během kompilace. Výchozí hodnota je `false`. Tento parametr odpovídá **-d** přepínač na aspnet_compiler.exe.|  
|`DelaySign`|Volitelné `Boolean` parametr.<br /><br /> Pokud tento parametr je `true`, sestavení není plně podepsáno při vytvoření.|  
|`FixedNames`|Volitelné `Boolean` parametr.<br /><br /> Pokud tento parametr je `true`, kompilované sestavení bude mu udělená pevné názvy...|  
|`Force`|Volitelné `Boolean` parametr<br /><br /> Pokud tento parametr je `true`, úloha přepíše cílový adresář, pokud již existuje. Dojde ke ztrátě stávajícího obsahu. Výchozí hodnota je `false`. Tento parametr odpovídá **-f** přepínač na aspnet_compiler.exe.|  
|`KeyContainer`|Volitelné `String` parametr.<br /><br /> Určuje kontejner klíče se silným názvem.|  
|`KeyFile`|Volitelné `String` parametr.<br /><br /> Určuje fyzickou cestu k souboru klíče silným názvem...|  
|`MetabasePath`|Volitelné `String` parametr.<br /><br /> Určuje úplnou cestu metabáze služby IIS aplikace. Tento parametr nelze kombinovat s `VirtualPath` nebo `PhysicalPath` parametry. Tento parametr odpovídá **-m** přepínač na aspnet_compiler.exe.|  
|`PhysicalPath`|Volitelné `String` parametr.<br /><br /> Určuje fyzickou cestu, která mají být zkompilovány, do aplikace. Pokud tento parametr chybí, metabáze služby IIS se používá k aplikaci. Tento parametr odpovídá **-p** přepínač na aspnet_compiler.exe.|  
|`TargetFrameworkMoniker`|Volitelné `String` parametr.<br /><br /> Určuje TargetFrameworkMoniker, která určuje, která verze rozhraní .NET Framework aspnet_compiler.exe by měl použít. Přijímá pouze monikery rozhraní .NET Framework.|  
|`TargetPath`|Volitelné `String` parametr.<br /><br /> Určuje fyzickou cestu, do kterého je aplikace zkompilovat. Pokud není zadaný, aplikace je předkompilovaných na místě.|  
|`Updateable`|Volitelné `Boolean` parametr.<br /><br /> Pokud tento parametr je `true`, předkompilované aplikace bude možné aktualizovat.  Výchozí hodnota je `false`. Tento parametr odpovídá **-u** přepínač na aspnet_compiler.exe.|  
|`VirtualPath`|Volitelné `String` parametr.<br /><br /> Virtuální cesta aplikace, které mají být zkompilovány, do. Pokud `PhysicalPath` zadán, fyzickou cestu slouží k vyhledání aplikace. Jinak hodnota se používá metabáze služby IIS a aplikace se předpokládá, že ve výchozím nastavení lokality. Tento parametr odpovídá **- v** přepínač na aspnet_compiler.exe.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.ToolTaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.ToolTask> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [tooltaskextension – základní třída](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu používá `AspNetCompiler` úloh předkompilovat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="PrecompileWeb">  
        <AspNetCompiler  
            VirtualPath="/MyWebSite"  
            PhysicalPath="c:\inetpub\wwwroot\MyWebSite\"  
            TargetPath="c:\precompiledweb\MyWebSite\"  
            Force="true"  
            Debug="true"  
        />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
