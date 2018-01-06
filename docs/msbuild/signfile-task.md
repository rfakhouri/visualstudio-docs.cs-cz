---
title: "Signfile – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#SignFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, SignFile task
- SignFile task [MSBuild]
ms.assetid: edef1819-ddeb-4e09-95de-fc7063ba9388
caps.latest.revision: "19"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8c1e5e25d6a8b3b953d28676415266ccf245d418
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="signfile-task"></a>SignFile – úloha
Zadaný soubor pomocí zadaný certifikát podepíše.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `SignFile` úloh.  
  
 Upozorňujeme, že algoritmus SHA-256 certifikáty jsou povolené jenom na počítačích, které mají .NET 4.5 nebo vyšší.  
  
> [!WARNING]
>  Od verze Visual Studio 2013 Update 3, tento úkol má nové podpis, který umožňuje zadat cílová verze framework pro soubor. Jste doporučujeme použít nový podpis, bez ohledu na to možné, protože proces MSBuild používá algoritmus SHA-256 hashuje pouze v případě, že cílové rozhraní je rozhraní .NET 4.5 nebo vyšší. Pokud cílové rozhraní .NET 4.0 nebo nižší než hodnota hash SHA-256 se nepoužijí.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`CertificateThumbprint`|Požadované `String` parametr.<br /><br /> Určuje certifikát, který chcete použít pro podepisování. Tento certifikát musí být v osobním úložišti aktuálního uživatele.|  
|`SigningTarget`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje soubory se přihlásit s certifikátem.|  
|`TimestampUrl`|Volitelné `String` parametr.<br /><br /> Určuje adresu URL časového razítka serveru.|  
|`TargetFrameworkVersion`|Verze rozhraní .NET Framework, který se používá pro cíl.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [Třída Base úlohy](../msbuild/task-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `SignFile` úkol podepsat soubory zadané v `FilesToSign` kolekce položek s certifikátem určeného `Certificate` vlastnost.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <FileToSign Include="File.exe" />  
    </ItemGroup>  
    <PropertyGroup>  
        <Certificate>Cert.cer</Certificate>  
    </PropertyGroup>  
    <Target Name="Sign">  
        <SignFile  
            CertificateThumbprint="$(CertificateThumbprint)"  
            SigningTarget="@(FileToSign)"   
            TargetFrameworkVersion="v4.5" />  
    </Target>  
</Project>  
```  
  
> [!NOTE]
>  Kryptografický otisk certifikátu je hash SHA-1 certifikátu. Další informace najdete v tématu [získat certifikát důvěryhodné kořenové Certifikační autority hodnotu Hash SHA-1](http://msdn.microsoft.com/en-us/dd641990-9a88-4228-a245-017797131a87).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `Exec` úkol podepsat soubory zadané v `FilesToSign` kolekce položek s certifikátem určeného `Certificate` vlastnost. Můžete použít k podepisování souborů Instalační služby systému Windows během procesu vytváření.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <FileToSign Include="File.msi" />  
    </ItemGroup>  
    <PropertyGroup>  
        <Certificate>Cert.cer</Certificate>  
    </PropertyGroup>  
    <Target Name="Sign">  
        <Exec Command="signtool.exe sign /f CertFile /p Password "@(FileToSign)" "/>  
        <SignFile  
            CertificateThumbprint="$(CertificateThumbprint)"  
            SigningTarget="@(FileToSign)"   
            TargetFrameworkVersion="v4.0" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)