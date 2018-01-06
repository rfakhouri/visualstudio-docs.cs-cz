---
title: "Šablony sady Visual Studio Manifest schéma – referenční informace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc7d0a81-0df5-41a9-a912-1b30e5da1d13
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 87f676ef30da7c667c4ce2b688520a49ed1931c3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-template-manifest-schema-reference"></a>Odkaz na manifestu schéma šablon sady Visual Studio
Toto schéma popisuje formát souborů manifestu (.vstman) šablony sady Visual Studio vygenerované šablony sady Visual Studio projektu nebo položky a umístění a další relevantní informace o šabloně.  
  
 : Protože existují samostatné položky a adresáře šablony projektu, manifest musí mít nikdy směs šablon položek a projektů.  
  
> [!IMPORTANT]
>  Tento manifest je k dispozici od Visual Studio 2017.  
  
## <a name="vstemplatemanifest-element"></a>VSTemplateManifest Element  
 Kořenový element manifestu.  
  
### <a name="attributes"></a>Atributy  
  
-   **Verze**: řetězec představující verze manifestu šablony. Požadováno.  
  
-   **Národní prostředí**: řetězec představující národního prostředí nebo národní prostředí manifestu šablony. Hodnota národního prostředí se vztahuje na všechny šablony, je nutné použít samostatné manifest pro každé národní prostředí. Volitelné.  
  
### <a name="child-elements"></a>Podřízené elementy  
  
-   **VSTemplateContainer** volitelné.  
  
-   **VSTemplateDir** volitelné.  
  
### <a name="parent-element"></a>Nadřazený element  
 Žádné  
  
## <a name="vstemplatecontainer"></a>VSTemplateContainer  
 Kontejner šablony manifest elementy. Manifest má jednoho kontejneru typu šablony ke každé šabloně, který definuje.  
  
### <a name="attributes"></a>Atributy  
 **VSTemplateType** : hodnotu řetězce, který určuje typ šablony (`"Project"`, `"Item"`, nebo `"ProjectGroup"`). Požadováno  
  
### <a name="child-elements"></a>Podřízené elementy  
  
-   **RelativePathOnDisk**: relativní cestu k souboru šablony na disku. Toto umístění také definuje umístění šablony ve stromu šablona ukazuje **nový projekt** nebo **nová položka** dialogové okno. Pro šablony nasadit jako jednotlivé soubory a adresáře Tato cesta odkazuje na adresář obsahující soubory šablon. Tato cesta pro šablony nasazena jako soubor ZIP, by měla být cesta k souboru .zip.  
  
-   **VSTemplateHeader** : A [TemplateData](../extensibility/templatedata-element-visual-studio-templates.md) element, který popisuje záhlaví.  
  
### <a name="parent-element"></a>Nadřazený element  
 **VSTemplateManifest**  
  
## <a name="vstemplatedir"></a>VSTemplateDir  
 Popisuje adresáře, kde je umístěný šablony. Manifest může obsahovat více **VSTemplateDir** položky zajistit lokalizovaný název a řazení řazení pro adresáře k řízení jejich vzhled ve stromu šablona kategorie.  
  
 Z důvodu jejich návrh **VSTemplateDir** položky by se zobrazit pouze v zadané manifesty – národní prostředí.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
-   **RelativePath**: cesta šablony. Může existovat jenom jeden záznam za cestu, takže první z nich bude win pro všechny manifesty.  
  
-   **LocalizedName**: A **NameDescriptionIcon** element, který určuje lokalizovaný název. Volitelné.  
  
-   **SortOrder** : řetězec, který určuje pořadí řazení. Volitelné.  
  
-   **ParentFolderOverrideName**: přepsaného název nadřazené složky. Volitelné. Tento element má **název** atribut, který je řetězcová hodnota, která určuje název.  
  
### <a name="parent-element"></a>Nadřazený element  
 **VSTemplateManifest**  
  
## <a name="namedescriptionicon"></a>NameDescriptionIcon  
 Určuje název a popis, které by mohly mít lokalizované šablony. V tématu **LocalizedName** výše.  
  
### <a name="attributes"></a>Atributy  
  
-   **Balíček**: řetězcovou hodnotu, která určuje balíček. Volitelné.  
  
-   **ID**: řetězcovou hodnotu, kterou určuje ID. Volitelné.  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-element"></a>Nadřazený element  
 **LocalizedName**  
  
## <a name="examples"></a>Příklady  
 Následuje příklad souboru .vstman šablony projektu.  
  
```xml  
<VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Project">  
    <RelativePathOnDisk>CSharp\1033\TestProjectTemplate</RelativePathOnDisk>  
    <TemplateFileName>TestProjectTemplate.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>TestProjectTemplate</Name>  
        <Description>TestProjectTemplate</Description>  
        <Icon>TestProjectTemplate.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <SortOrder>1000</SortOrder>  
        <TemplateID>aac0aeea-7883-4003-992f-937d53d70ab1</TemplateID>  
        <CreateNewFolder>true</CreateNewFolder>  
        <DefaultName>TestProjectTemplate</DefaultName>  
        <ProvideDefaultName>true</ProvideDefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```  
  
 Následuje příklad položky šablony .vstman souboru.  
  
```  
VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Item">  
    <RelativePathOnDisk>CSharp\1033\ItemTemplate1</RelativePathOnDisk>  
    <TemplateFileName>ItemTemplate1.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>ItemTemplate1</Name>  
        <Description>ItemTemplate1</Description>  
        <Icon>ItemTemplate1.ico</Icon>  
        <TemplateID>bfeadf8e-a251-4109-b605-516b88e38c8d</TemplateID>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <DefaultName>Class.cs</DefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```