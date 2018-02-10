---
title: "Postupy: referenční projektu MSBuild SDK | Microsoft Docs"
ms.custom: 
ms.date: 01/25/2018
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, SDKs, SDK
author: jeffkl
ms.author: jeffkl
manager: angerlic
ms.workload:
- multiple
ms.openlocfilehash: 28027b21d3f562e3eda94dc91de16ddb38362d3c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-use-msbuild-project-sdks"></a>Postupy: použití sady SDK projektu nástroje MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 15.0 zaveden koncept "projektu SDK", což zjednodušuje použití software development Kit, které vyžadují vlastnosti a cíle určených k importu.

```xml
<Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
        <TargetFramework>net46</TargetFramework>
    </PropertyGroup>
</Project>
```  
  
Během testování projektu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] přidá implicitní importy v horní a dolní části projektu:

```xml
<Project>
    <!-- Implicit top import -->
    <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />

    <PropertyGroup>
        <TargetFramework>net46</TargetFramework>
    </PropertyGroup>

    <!-- Implicit bottom import -->
    <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>  
```  

## <a name="referencing-a-project-sdk"></a>Odkazování na projekt SDK
 Existují tři způsoby, jak odkazovat na projekt SDK

1. Použití `Sdk` atributu u `<Project/>` element:
    ```xml
    <Project Sdk="My.Custom.Sdk">
        ...
    </Project>
    ```
    Implicitní importu se přidá do horní a dolní projektu jak je popsáno výše.  Formát `Sdk` atribut je `Name[/Version]` kde verze je volitelné.  Například můžete zadat `My.Custom.Sdk/1.2.3`.

2. Použít nejvyšší úrovně `<Sdk/>` element:
    ```xml
    <Project>
        <Sdk Name="My.Custom.Sdk" Version="1.2.3" />
        ...
    </Project>
   ```
   Implicitní importu se přidá do horní a dolní projektu jak je popsáno výše.  `Version` Atribut se nevyžaduje.

3. Použití `<Import/>` element kdekoli v projektu:
    ```xml
    <Project>
        <PropertyGroup>
            <MyProperty>Value</MyProperty>
        </PropertyGroup>
        <Import Project="Sdk.props" Sdk="My.Custom.Sdk" />
        ...
        <Import Project="Sdk.targets" Sdk="My.Custom.Sdk" />
    </Project>
   ```
   Explicitně včetně importy ve vašem projektu umožňuje plnou kontrolu nad pořadí.

   Při použití `<Import/>` elementu, můžete zadat volitelný `Version` také atribut.  Například můžete zadat `<Import Project="Sdk.props" Sdk="My.Custom.Sdk" Version="1.2.3" />`.

## <a name="how-project-sdks-are-resolved"></a>Způsob řešení projektu sady SDK
Při vyhodnocování importu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] dynamicky přeloží cestu k projektu SDK podle názvu a verze, které jste zadali.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]také obsahuje seznam registrovaných překladačů SDK, které jsou zásuvné moduly, které najít projekt sady SDK na váš počítač.  Tyto moduly plug-in patří:

1. Překladač na základě NuGet, který se dotazuje vašeho nakonfigurované balíčku informační kanály pro balíčky NuGet, které odpovídají ID a verzi sady SDK, které jste zadali.<br/>
   Tento překladač je aktivní, pouze pokud jste zadali ve verzi volitelné a lze použít pro všechny vlastní projekt SDK.  
2. Překladač rozhraní příkazového řádku .NET, která přeloží sady SDK, které jsou nainstalované s .NET rozhraní příkazového řádku.<br/>
   Tento překladač vyhledá projektu sady SDK, jako `Microsoft.NET.Sdk` a `Microsoft.NET.Sdk.Web` které jsou součástí produktu.
3. Výchozí překladač, která přeloží sady SDK, které byly nainstalované pomocí nástroje MSBuild.

Překladač na základě NuGet sady SDK podporuje určení verze ve vaší [global.json](https://docs.microsoft.com/en-us/dotnet/core/tools/global-json) , které umožňuje uživateli řídit verze sady SDK projektu na jednom místě, ne ve všech projektech:

```json
{
    "msbuild-sdks": {
        "My.Custom.Sdk": "5.0.0",
        "My.Other.Sdk": "1.0.0-beta"
    }
}
```
Jenom jedna verze jednotlivých projektů sady SDK můžete použít během sestavení.  Pokud je odkazováno na dvě různé verze stejného projektu sady SDK, bude MSBuild posílat upozornění.  Doporučuje se **není** zadejte verzi v projektech, pokud je verze zadané v vaší `global.json`.  

## <a name="see-also"></a>Viz také  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Přizpůsobení buildu](../msbuild/customize-your-build.md)   
