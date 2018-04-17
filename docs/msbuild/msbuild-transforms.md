---
title: Transformace nástroje MSBuild | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bcfc3c-14fa-455e-805c-63ccffa4a3bf
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eff5d0a3d01417ec065b15fe324b7f554cccb287
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="msbuild-transforms"></a>Transformace nástroje MSBuild
Transformace je 1: 1 převod jednu položku seznamu do jiného. Kromě povolení projektu převést položek seznamů, umožňuje transformace cíl k identifikaci přímého mapování mezi jeho vstupů a výstupů. Toto téma vysvětluje, transformace a jak [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] je používá k vytvoření projektů efektivněji.  
  
## <a name="transform-modifiers"></a>Modifikátory transformace  
Transformace nejsou libovolný, ale mají omezenou speciální syntaxi, ve kterém všechny modifikátory transformace musí být ve formátu %(*ItemMetaDataName*). Veškerá metadata položky můžete použít jako modifikátoru transformace. To zahrnuje metadata známé položky, přiřazený každá položka při jeho vytvoření. Seznam známá metadata položky, naleznete v části [Metadata známé položky](../msbuild/msbuild-well-known-item-metadata.md).  
  
V následujícím příkladu, seznam *RESX* soubory transformována do seznamu *.resources* soubory. Modifikátor transformace %(filename) určuje, aby se každý *.resources* soubor má stejný název jako odpovídající *RESX* souboru.  
  
```  
@(RESXFile->'%(filename).resources')  
```

Například, pokud jsou položky v seznamu položek @(RESXFile) *Form1.resx*, *Form2.resx*, a *Form3.resx*, bude výstupy v seznamu transformovaných  *Form1.Resources*, *Form2.resources*, a *Form3.resources*.  

> [!NOTE]
>  Stejným způsobem zadejte oddělovač pro standardní položky seznamu můžete zadat vlastní oddělovače transformovaných položky seznamu. Například samostatné seznam transformovaných položky oddělte čárkou (,) namísto výchozí středníkem (;), použijte následující kód XML:  
> `@(RESXFile->'Toolset\%(filename)%(extension)', ',')`
  
## <a name="using-multiple-modifiers"></a>Použití více modifikátory  
 Výraz transformace může obsahovat více modifikátory, které mohou být kombinovány v libovolném pořadí a lze je opakovat. V následujícím příkladu se změnil název adresáře, který obsahuje soubory, ale soubory zachovat původní přípona názvu název a souboru.  
  
```  
@(RESXFile->'Toolset\%(filename)%(extension)')  
```  
  
 Například, pokud položky, které jsou součástí `RESXFile` seznamu položek jsou *Project1\Form1.resx*, *Project1\Form2.resx*, a *Project1\Form3.text*, výstupy v seznamu transformovaných bude *Toolset\Form1.resx*, *Toolset\Form2.resx*, a *Toolset\Form3.text*.  
  
## <a name="dependency-analysis"></a>Analýza závislostí  
 Transformace zaručit mapování 1: 1 mezi transformovaných položky seznamu a původní seznam položek. Proto v případě, že cíl vytvoří výstupů, které jsou transformací vstupních hodnot, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] můžete analyzovat časová razítka vstupy a výstupy a rozhodnout, zda chcete přeskočit, sestavení nebo částečně znovu sestavit cíl.  
  
 V [úlohy kopie](../msbuild/copy-task.md) v následujícím příkladu každý soubor v `BuiltAssemblies` seznamu položek mapy do souboru v cílové složce úlohy, při použití transformace v zadat `Outputs` atribut. Pokud soubor v `BuiltAssemblies` položky seznamu změny `Copy` úkolů spouští pouze pro změněný soubor a všechny ostatní soubory se přeskočí. Další informace o detekci závislosti a o používání transformace najdete v tématu [postupy: sestavení postupně](../msbuild/how-to-build-incrementally.md).  
  
```xml  
<Target Name="CopyOutputs"  
    Inputs="@(BuiltAssemblies)"  
    Outputs="@(BuiltAssemblies -> '$(OutputPath)%(Filename)%(Extension)')">  
  
    <Copy  
        SourceFiles="@(BuiltAssemblies)"  
        DestinationFolder="$(OutputPath)"/>  
  
</Target>  
```  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] soubor projektu, který používá transformací. Tento příklad předpokládá, že je v adresáři c:\sub0\sub1\sub2\sub3 jenom jeden soubor XSD a zda pracovní adresář c:\sub0.  
  
### <a name="code"></a>Kód  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Schema Include="sub1\**\*.xsd"/>  
    </ItemGroup>  
  
    <Target Name="Messages">  
        <Message Text="rootdir: @(Schema->'%(rootdir)')"/>  
        <Message Text="fullpath: @(Schema->'%(fullpath)')"/>  
        <Message Text="rootdir + directory + filename + extension: @(Schema->'%(rootdir)%(directory)%(filename)%(extension)')"/>  
        <Message Text="identity: @(Schema->'%(identity)')"/>  
        <Message Text="filename: @(Schema->'%(filename)')"/>  
        <Message Text="directory: @(Schema->'%(directory)')"/>  
        <Message Text="relativedir: @(Schema->'%(relativedir)')"/>  
        <Message Text="extension: @(Schema->'%(extension)')"/>  
    </Target>  
</Project>  
```  
  
### <a name="comments"></a>Komentáře  
 Tento příklad vytvoří následující výstup:  
  
```  
rootdir: C:\  
fullpath: C:\xmake\sub1\sub2\sub3\myfile.xsd  
rootdir + directory + filename + extension: C:\xmake\sub1\sub2\sub3\myfile.xsd  
identity: sub1\sub2\sub3\myfile.xsd  
filename: myfile  
directory: xmake\sub1\sub2\sub3\  
relativedir: sub1\sub2\sub3\  
extension: .xsd  
```  
  
## <a name="see-also"></a>Viz také  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Postupy: Přírůstkové sestavování](../msbuild/how-to-build-incrementally.md)