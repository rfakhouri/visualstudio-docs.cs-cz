---
title: "Postupy: vytváření šablon vícenásobného projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, creating multi-project templates
- project templates, creating multi-project templates
- multi-project templates
ms.assetid: 8c7f7065-137e-40ad-868d-37e007270efd
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9d4ffd6c3aa23ebc2b801de2d581876ff5afd480
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-multi-project-templates"></a>Postupy: Vytváření šablon vícenásobného projektu
Šablony vícenásobných projektů slouží jako kontejnery pro dva nebo více projektů. Když na projekt na základě vícenásobného projektu šablony je vytvořený z **nový projekt** dialogové okno, všechny projekty v šabloně je přidán do řešení.  
  
 Šablonu vícenásobného projektu musí zahrnovat následující položky, komprimované do souboru .zip:  
  
-   Kořenový soubor .vstemplate celý vícenásobného projektu šablony. Tento kořenový soubor .vstemplate obsahuje metadata, která **nový projekt** dialogové okno zobrazí a určuje, kde se mají hledat soubory .vstemplate pro projekty v této šabloně. Tento soubor musí být umístěn v kořenovém adresáři souboru ZIP.  
  
-   Jeden nebo více složek, které obsahují soubory, které jsou požadovány pro šablonu dokončený projekt. To zahrnuje všechny soubory kódu pro projekt a také soubor .vstemplate pro projekt.  
  
 Například soubor .zip vícenásobného projektu šablony, která má dva projekty může mít následující soubory a adresáře:  
  
 MultiProjectTemplate.vstemplate  
  
 \Project1\Project1.vstemplate  
  
 \Project1\Project1.vbproj  
  
 \Project1\Class.vb  
  
 \Project2\Project2.vstemplate  
  
 \Project2\Project2.vbproj  
  
 \Project2\Class.vb  
  
 V kořenovém souboru .vstemplate pro šablonu vícenásobného projektu se liší od jednoprojektové šablony následujícími způsoby:  
  
-   `Type` Atribut `VSTemplate` element obsahuje hodnotu `ProjectGroup`. Příklad:  
  
    ```  
    <VSTemplate Version="2.0.0" Type="ProjectGroup"  
        xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    ```  
  
-   `TemplateContent` Obsahuje element `ProjectCollection` element, který má jeden nebo více `ProjectTemplateLink` prvků, které definují cesty k souborům .vstemplate zahrnutých projektů. Příklad:  
  
    ```  
    <TemplateContent>  
        <ProjectCollection>  
            <ProjectTemplateLink>  
                Project1\Project1.vstemplate  
            </ProjectTemplateLink>  
            <ProjectTemplateLink>  
                Project2\Project2.vstemplate  
            </ProjectTemplateLink>  
        </ProjectCollection>  
    </TemplateContent>  
    ```  
  
 Šablon vícenásobného projektu také chovat jinak než normální šablony. Šablon vícenásobného projektu mají následující jedinečné vlastnosti:  
  
-   Jednotlivých projektů v šabloně vícenásobného projektu nelze přiřadit názvy **nový projekt** dialogové okno. Místo toho použijte `ProjectName` atributu u `ProjectTemplateLink` elementu, který chcete zadat název pro každý projekt. Další informace najdete v tématu v prvním příkladu v následující části.  
  
-   Šablon vícenásobného projektu může obsahovat projekty, které jsou napsané v různých jazycích, ale celá samotná šablona může být uvedena pouze v jedné kategorii pomocí `ProjectType` elementu.  
  
### <a name="to-create-a-multi-project-template"></a>Chcete-li vytvořit šablonu vícenásobného projektu  
  
1.  Vytváření projektů, které chcete zahrnout do šablony vícenásobného projektu.  
  
2.  Vytvořte soubory .vstemplate pro každý projekt. Další informace najdete v tématu [postupy: vytvoření šablony projektů](../ide/how-to-create-project-templates.md).  
  
3.  Vytvořte soubor .vstemplate kořenové, obsahující metadata pro šablony vícenásobného projektu. Další informace najdete v tématu v prvním příkladu v následující části.  
  
4.  Vyberte soubory a složky, do šablony zahrnout, klikněte pravým tlačítkem na výběr, klikněte na tlačítko **odeslat**a potom klikněte na **komprimované složky (ZIP)**. Soubory a složky jsou komprimovány do souboru ZIP.  
  
5.  Vložte soubor .zip šablony do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] adresáře šablony projektu. Ve výchozím nastavení, je tento adresář Documents\Visual Studio *verze*\Templates\ProjectTemplates\\.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje základní kořenový vícenásobného projektu soubor .vstemplate. V tomto příkladu šablona obsahuje dva projekty `My Windows Application` a `My Class Library`. `ProjectName` Atributu u `ProjectTemplateLink` element nastaví název pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] k přiřazení tohoto projektu. Pokud `ProjectName` atribut neexistuje, název souboru .vstemplate slouží jako název projektu.  
  
```  
<VSTemplate Version="2.0.0" Type="ProjectGroup"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-Project Template Sample</Name>  
        <Description>An example of a multi-project template</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectCollection>  
            <ProjectTemplateLink ProjectName="My Windows Application">  
                WindowsApp\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
            <ProjectTemplateLink ProjectName="My Class Library">  
                ClassLib\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
        </ProjectCollection>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `SolutionFolder` elementu, který chcete rozdělit do dvou skupin, projektů `Math Classes` a `Graphics Classes`. Šablona obsahuje čtyři projekty, dvě z nich jsou umístěny ve složce každé řešení.  
  
```  
<VSTemplate Version="2.0.0" Type="ProjectGroup"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-Project Template Sample</Name>  
        <Description>An example of a multi-project template</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectCollection>  
            <SolutionFolder Name="Math Classes">  
                <ProjectTemplateLink ProjectName="MathClassLib1">  
                    MathClassLib1\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
                <ProjectTemplateLink ProjectName="MathClassLib2">  
                    MathClassLib2\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
            </SolutionFolder>  
            <SolutionFolder Name="Graphics Classes">  
                <ProjectTemplateLink ProjectName="GraphicsClassLib1">  
                    GraphicsClassLib1\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
                <ProjectTemplateLink ProjectName="GraphicsClassLib2">  
                    GraphicsClassLib2\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
            </SolutionFolder>  
        </ProjectCollection>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Viz také  
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Postupy: vytváření šablon projektu](../ide/how-to-create-project-templates.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [SolutionFolder – Element (šablony sady Visual Studio)](../extensibility/solutionfolder-element-visual-studio-templates.md)   
 [ProjectTemplateLink – Element (šablony sady Visual Studio)](../extensibility/projecttemplatelink-element-visual-studio-templates.md)