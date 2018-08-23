---
title: Signfile – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#SignFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, SignFile task
- SignFile task [MSBuild]
ms.assetid: edef1819-ddeb-4e09-95de-fc7063ba9388
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e0c8df375f9f4024ca4e055c53e8d114378ac32e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666939"
---
# <a name="signfile-task"></a>SignFile – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [signfile – úloha](https://docs.microsoft.com/visualstudio/msbuild/signfile-task).  
  
  
Zaregistruje zadaného souboru pomocí zadaného certifikátu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `SignFile` úloh.  
  
 Všimněte si, že jsou certifikáty SHA-256 povolených jenom na počítače, které mají rozhraní .NET 4.5 a vyšší.  
  
> [!WARNING]
>  Od verze Visual Studio 2013 Update 3, tento úkol má nový podpis, který vám umožní určit cílovou architekturu na verzi souboru. Jste ukončena. doporučujeme používat nový podpis, bez ohledu na to možné, protože procesu MSBuild používá algoritmus SHA-256 hashuje pouze pokud je cílové rozhraní .NET 4.5 nebo vyšší. Pokud je verze cílového rozhraní .NET 4.0 nebo dole, se nepoužije hashovací algoritmus SHA-256.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`CertificateThumbprint`|Vyžaduje `String` parametru.<br /><br /> Určuje certifikát, který chcete použít pro podepisování. Tento certifikát musí být v osobním úložišti aktuálního uživatele.|  
|`SigningTarget`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje soubory, které chcete podepsat pomocí certifikátu.|  
|`TimestampUrl`|Volitelné `String` parametru.<br /><br /> Určuje adresu URL časového razítka serveru.|  
|`TargetFrameworkVersion`|Verze rozhraní .NET Framework, který se používá pro cíl.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [Třída Base úlohy](../msbuild/task-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `SignFile` úloh se soubory v zadané `FilesToSign` kolekci položek s certifikátem určené `Certificate` vlastnost.  
  
```  
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
>  Kryptografický otisk certifikátu je hodnota hash SHA-1 certifikátu. Další informace najdete v tématu [získat hodnoty Hash SHA-1 certifikátu důvěryhodné kořenové certifikační Autority](http://msdn.microsoft.com/en-us/dd641990-9a88-4228-a245-017797131a87).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `Exec` úloh se soubory v zadané `FilesToSign` kolekci položek s certifikátem určené `Certificate` vlastnost. To můžete použít k podepsání soubory Instalační služby systému Windows během procesu sestavení.  
  
```  
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



