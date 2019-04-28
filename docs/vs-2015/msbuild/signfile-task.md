---
title: Signfile – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
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
manager: jillfra
ms.openlocfilehash: 081899efb202917f1ebeac97a58dd89cf5a04f53
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63444393"
---
# <a name="signfile-task"></a>SignFile – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zaregistruje zadaného souboru pomocí zadaného certifikátu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `SignFile` úloh.  
  
 Všimněte si, že jsou certifikáty SHA-256 povolených jenom na počítače, které mají rozhraní .NET 4.5 a vyšší.  
  
> [!WARNING]
> Od verze Visual Studio 2013 Update 3, tento úkol má nový podpis, který vám umožní určit cílovou architekturu na verzi souboru. Jste ukončena. doporučujeme používat nový podpis, bez ohledu na to možné, protože procesu MSBuild používá algoritmus SHA-256 hashuje pouze pokud je cílové rozhraní .NET 4.5 nebo vyšší. Pokud je verze cílového rozhraní .NET 4.0 nebo dole, se nepoužije hashovací algoritmus SHA-256.  
  
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
> Kryptografický otisk certifikátu je hodnota hash SHA-1 certifikátu. Další informace najdete v tématu [získat hodnoty Hash SHA-1 certifikátu důvěryhodné kořenové certifikační Autority](http://msdn.microsoft.com/dd641990-9a88-4228-a245-017797131a87).  
  
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
