---
title: "GenerateBootstrapper – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GenerateBootstrapper
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GenerateBootstrapper task
- GenerateBootstrapper task [MSBuild]
ms.assetid: ca3ba2c6-d2ea-41f2-b7e3-0fc2b0730460
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3feb529b76b9de8c70b87954e928a75158361f6b
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="generatebootstrapper-task"></a>GenerateBootstrapper – úloha
Poskytuje automatizovaný způsob, jak zjistit, stáhnout a nainstalovat aplikace a její požadované součásti. Slouží jako jeden instalační program, který se integruje se samostatný instalační programy pro všechny součásti tvořící aplikaci.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `GenerateBootstrapper` úloh.  
  
-   `ApplicationFile`  
  
     Volitelné `String` parametr.  
  
     Určuje soubor, který bude používat zavaděč po byly nainstalovány všechny požadované součásti, spusťte instalaci aplikace. Chyby sestavení dojde, pokud `BootstrapperItems` ani `ApplicationFile` je zadán parametr.  
  
-   `ApplicationName`  
  
     Volitelné `String` parametr.  
  
     Určuje název aplikace, který bude instalovat zaváděcí nástroj. Tento název se zobrazí v uživatelském rozhraní zavaděč používá během instalace.  
  
-   `ApplicationRequiresElevation`  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, součást běží se zvýšenými oprávněními na cílovém počítači nainstalovaný.  
  
-   `ApplicationUrl`  
  
     Volitelné `String` parametr.  
  
     Určuje umístění Web, který je hostitelem aplikace Instalační služby.  
  
-   `BootstrapperComponentFiles`  
  
     Volitelné `String[]` výstupní parametr.  
  
     Určuje umístění vytvořené soubory balíčku zaváděcího nástroje.  
  
-   `BootstrapperItems`  
  
     Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.  
  
     Určuje produkty, které sestavení do zaváděcího nástroje. Položek předaných tento parametr musí mít následující syntaxi:  
  
    ```xml  
    <BootstrapperItem  
        Include="ProductCode">  
        <ProductName>  
            ProductName  
        </ProductName>  
    </BootstrapperItem>  
    ```  
  
     `Include` Atribut se používá k reprezentování název požadovaných součástí, které by měly být nainstalovány. `ProductName` Metadata položky je volitelná a použije modul sestavení jako uživatelské jméno v případě, že balíček nebyl nalezen. Tyto položky nejsou nutné [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vstupní parametry, pokud žádné `ApplicationFile` je zadán. Pro vaše aplikace by měla obsahovat jednu položku pro každý požadavek, který se musí nainstalovat.  
  
     Chyby sestavení dojde, pokud `BootstrapperItems` ani `ApplicationFile` je zadán parametr.  
  
-   `BootstrapperKeyFile`  
  
     Volitelné `String` výstupní parametr.  
  
     Určuje umístění vytvořené setup.exe  
  
-   `ComponentsLocation`  
  
     Volitelné `String` parametr.  
  
     Určuje umístění pro zavaděč hledání požadavky pro instalaci k instalaci. Tento parametr může mít následující hodnoty::  
  
    -   `HomeSite`: Určuje, že je předpokladů hostované dodavatelem součásti.  
  
    -   `Relative`: Označuje, že preqrequisite je ve stejném umístění aplikace.  
  
    -   `Absolute`: Určuje, že všechny součásti se nachází na centralizované adrese URL. Tato hodnota by měla být používá ve spojení s `ComponentsUrl` vstupní parametr.  
  
     Pokud `ComponentsLocation` není zadán, `HomeSite` se používá ve výchozím nastavení.  
  
-   `ComponentsUrl`  
  
     Volitelné `String` parametr.  
  
     Určuje adresu URL obsahující požadavky pro instalaci.  
  
-   `CopyComponents`  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, zavaděč zkopíruje všechny výstupní soubory do cesty zadané v `OutputPath` parametr. Hodnoty `BootstrapperComponentFiles` parametru by měla všechny být založena na této cestě. Pokud `false`, nejsou soubory zkopírovali a `BootstrapperComponentFiles` hodnoty jsou založeny na hodnotu `Path` parametr.  Výchozí hodnota tohoto parametru je `true`.  
  
-   `Culture`  
  
     Volitelné `String` parametr.  
  
     Určuje jazykovou verzi, která používá pro zaváděcího nástroje uživatelského rozhraní a požadavky na instalaci. Pokud zadaná jazyková verze je k dispozici, úloha používá hodnotu `FallbackCulture` parametr.  
  
-   `FallbackCulture`  
  
     Volitelné `String` parametr.  
  
     Určuje sekundární jazykovou verzi, která používá pro bootstraper uživatelského rozhraní a požadavky na instalaci.  
  
-   `OutputPath`  
  
     Volitelné `String` parametr.  
  
     Určuje umístění pro kopírování setup.exe a všechny soubory balíčku.  
  
-   `Path`  
  
     Volitelné `String` parametr.  
  
     Určuje umístění všechny dostupné požadované balíčky.  
  
-   `SupportUrl`  
  
     Volitelné `String` parametr.  
  
     Určuje adresu URL k poskytování má selhat instalace zaváděcího nástroje  
  
-   `Validate`  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, zavaděč provede ověření XSD na zadaný vstupní zaváděcího nástroje položky. Výchozí hodnota tohoto parametru je `false`.  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `GenerateBootstrapper` úloh, které chcete nainstalovat aplikaci, kterou musí mít [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] nainstalovat požadovanou součástí.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <BootstrapperFile Include="Microsoft.Net.Framework.2.0">  
            <ProductName>Microsoft .NET Framework 2.0</ProductName>  
        </BootstrapperFile>  
    </ItemGroup>  
  
    <Target Name="BuildBootstrapper">  
        <GenerateBootstrapper  
            ApplicationFile="WindowsApplication1.application"  
            ApplicationName="WindowsApplication1"  
            ApplicationUrl="http://mycomputer"  
            BootstrapperItems="@(BootstrapperFile)"  
            OutputPath="C:\output" />  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)