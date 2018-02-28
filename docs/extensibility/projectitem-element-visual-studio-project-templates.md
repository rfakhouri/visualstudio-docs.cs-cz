---
title: "ProjectItem – Element (šablony projektů Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem
helpviewer_keywords:
- ProjectItem element [Visual Studio project templates]
- <ProjectItem> element [Visual Studio project templates]
ms.assetid: 82879fbe-7756-42cd-9a07-c10edf5b4673
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ca5143a3e5eaff488fee89b643a40adb60473bd8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="projectitem-element-visual-studio-project-templates"></a>ProjectItem – element (šablony projektů Visual Studio)
Určuje soubor, který je součástí projektu šablony.  
  
> [!NOTE]
>  `ProjectItem` Element přijímá různé atributy v závislosti na tom, jestli je šablona pro projekt nebo položku. Toto téma vysvětluje `ProjectItem` element pro šablony projektů. Další informace o `ProjectItem` element pro šablony položek, najdete v části [ProjectItem – Element (šablony Visual Studia položky)](../extensibility/projectitem-element-visual-studio-item-templates.md).  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Projekt >  
 \<ProjectItem – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProjectItem  
    TargetFileName="TargetFileName.ext"  
    ReplaceParameters="true/false"  
    OpenInEditor="true/false"  
    OpenInWebBrowser="true/false"  
    OpenInHelpBrowser="true/false"  
    OpenOrder="Value">  
        FileName.ext  
</ProjectItem>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`TargetFileName`|Nepovinný atribut.<br /><br /> Určuje název a cesta položky projektu, když na projekt je vytvořený z šablony. Tento atribut je užitečná pro vytváření liší od strukturu adresáře do struktury adresářů v souboru ZIP šablony, nebo pro vytvoření název položky pomocí nahrazení parametru.|  
|`ReplaceParameters`|Nepovinný atribut.<br /><br /> Logická hodnota, která určuje, zda je položka hodnoty parametrů, které se musí nahradit při vytváření projektu ze šablony. Výchozí hodnota je `false`.|  
|`OpenInEditor`|Nepovinný atribut.<br /><br /> Logická hodnota, která určuje, zda položka musí být otevřen v jeho odpovídající editoru v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vytvoření projektu ze šablony.<br /><br /> `OpenInWebBrowser` a `OpenInHelpBrowser` atributy jsou ignorovány u položky s `OpenInEditor` hodnotu `true`.<br /><br /> Výchozí hodnota je `false`.|  
|`OpenInWebBrowser`|Nepovinný atribut.<br /><br /> Logická hodnota, která určuje, zda položku by měla otevřít webový prohlížeč při vytváření projektu ze šablony.<br /><br /> Pouze soubory HTML a textové soubory, které jsou místní vzhledem k projektu můžete otevřít ve webovém prohlížeči. Externí adresy URL nejde otevřít pomocí tohoto atributu.<br /><br /> Výchozí hodnota je `false`.|  
|`OpenInHelpBrowser`|Nepovinný atribut.<br /><br /> Logická hodnota, která určuje, zda položka musí být otevřen v okně nápovědy, při vytváření projektu ze šablony.<br /><br /> Pouze soubory HTML a textové soubory, které jsou místní vzhledem k projektu lze otevřít v prohlížeči. Externí adresy URL nejde otevřít pomocí tohoto atributu.<br /><br /> Výchozí hodnota je `false`.|  
|`OpenOrder`|Nepovinný atribut.<br /><br /> Určuje číselnou hodnotu, která představuje pořadí, že položky se otevřou v jejich odpovídajících editory. Všechny hodnoty musí být násobky čísla 10. Položky s vyšší `OpenOrder` hodnoty jsou otevřená.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Projekt](../extensibility/project-element-visual-studio-templates.md)|Určuje soubory nebo adresáře, které chcete přidat do projektu.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 A `string` představující název nebo cesta k souboru v souboru ZIP šablony.  
  
## <a name="remarks"></a>Poznámky  
 `ProjectItem`je volitelné podřízeným `Project`.  
  
 `TargetFileName` Atributu lze vytvořit liší od strukturu adresáře do struktury adresářů v souboru ZIP šablony. Například pokud soubor `MyFile.vb` existuje v kořenovém souboru .zip, šablony, ale chcete soubor umístit do adresáře s názvem `CustomFiles` na všechny projekty vytvořené ze šablony, byste použili následující kód XML:  
  
```  
<ProjectItem TargetFileName="CustomFiles\MyFile.vb">MyFile.vb</ProjectItem>  
```  
  
 `TargetFileName` Atribut můžete také použít k přejmenování souborů, které obsahují mezinárodní znaky v jejich názvy souborů. Soubor .zip šablony například nemůže obsahovat názvy souborů s znaky znakové sady Unicode, takže soubor musí přejmenovat, než mohou být komprimovány do souboru .zip. `TargetFileName` Atribut lze nastavit název souboru zpět na původní název souboru ve formátu Unicode.  
  
 `TargetFileName` Atribut můžete také použít k přejmenování souborů s parametry. Následující postup vysvětluje, jak chcete přejmenovat soubor `MyFile.vb`, která existuje v kořenovém adresáři souboru ZIP šablony s názvem souboru na základě názvu projektu.  
  
### <a name="to-rename-files-with-parameters"></a>K přejmenování souborů s parametry  
  
1.  Použijte následující kód XML v souboru .vstemplate:  
  
    ```  
    <ProjectItem TargetFileName="$safeprojectname$.vb">MyFile.vb</ProjectItem>  
    ```  
  
2.  Otevřete soubor projektu (.vbproj pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekt) v textovém editoru nebo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
3.  Vyhledejte řádek v souboru projektu, který vypadá podobně jako následující kód XML:  
  
    ```  
    <Compile Include="MyFile.vb">  
    ```  
  
4.  Řádek kódu nahraďte následující kód XML:  
  
    ```  
    <Compile Include="$safeprojectname$.vb">  
    ```  
  
     Když na projekt je vytvořené z této šablony, názvu souboru bude vycházet uživatel zadaný v název **nový projekt** dialogové okno, se všemi nebezpečné znaky a odebrány mezery. Další informace najdete v tématu [parametry šablony](../ide/template-parameters.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metadata pro šablona projektu pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] aplikace.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyStarterKit.csproj">  
            <ProjectItem ReplaceParameters="true">Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Parametry šablony](../ide/template-parameters.md)   
 [ProjectItem – element (šablony sady Visual Studio)](../extensibility/projectitem-element-visual-studio-item-templates.md)