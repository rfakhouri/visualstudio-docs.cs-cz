---
title: Použití spravovaných balíček Framework pro typ projektu (C#) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], creating with MPF
- MPF projects
- managed package framework, creating projects
ms.assetid: 926de536-eead-415b-9451-f1ddc8c44630
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 112988f28728d40509a3af0360246a6bb4caef1a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31140200"
---
# <a name="using-the-managed-package-framework-to-implement-a-project-type-c"></a>Použití rozhraní spravované balíček k implementaci typu projektu (C#)
Spravované balíček Framework (MPF) poskytuje třídy jazyka C# můžete použít nebo dědí implementovat vlastní typy projektů. Sady MPF mnoho rozhraní sady Visual Studio očekává typu projektu zajistit, implementuje, můžete ponechat volné soustředit na implementaci údaje o typu vašeho projektu.  
  
## <a name="using-the-mpf-project-source-code"></a>Pomocí sady MPF projektů zdrojového kódu  
 Spravovaná rozhraní balíčku pro projekty (MPFProj) poskytuje pomocné třídy pro vytváření a správu nového projektu systému. Na rozdíl od jiné třídy v MPF třídy projektu nejsou součástí sestavení dodaný pomocí sady Visual Studio. Místo toho jsou uvedeny třídy projektu jako zdrojový kód v [sady MPF projektů 2013](http://mpfproj12.codeplex.com).  
  
 Chcete-li přidat tento projekt pro vaše řešení VSPackage, postupujte takto:  
  
1.  Stáhnout soubory MPFProj *MPFProjectDir*.  
  
2.  V *MPFProjectDir*\Dev10\Src\CSharp\ProjectBase.file, změňte následující blok:  
  
```  
<!-- Provide a default value for $(ProjectBasePath) -->  
  <PropertyGroup>  
    <ProjectBasePath >MPFProjDir\Dev10\Src\CSharp</ProjectBasePath>  
  </PropertyGroup>  
```  
  
1.  Vytvoření projektu VSPackage.  
  
2.  Uvolnění VSPackage projektu.  
  
3.  Upravte soubor .csproj VSPackage přidáním následující blok před dalších `<Import>` bloky:  
  
```  
<Import Project="MPFProjectDir\Dev10\Src\CSharp\ProjectBase.files" />  
  <PropertyGroup>  
    <!--To specify a different registry root to register your package, uncomment the TargetRegistryRoot tag and specify a registry root in it.  
    <TargetRegistryRoot></TargetRegistryRoot>-->  
    <RegisterOutputPackage>true</RegisterOutputPackage>  
    <RegisterWithCodebase>true</RegisterWithCodebase>  
  </PropertyGroup>  
```  
  
1.  Uložte projekt.  
  
2.  Zavřete a znovu otevřete VSPackage řešení.  
  
3.  Otevřete projekt VSPackage. Měli byste vidět nový adresář s názvem ProjectBase.  
  
4.  Přidejte následující odkaz na projekt VSPackage:  
  
     Microsoft.Build.Tasks.4.0  
  
5.  Sestavte projekt.  
  
## <a name="hierarchy-classes"></a>Hierarchie tříd  
 Následující tabulka shrnuje třídy v MPFProj, které podporují projektu hierarchií. Další informace najdete v tématu [hierarchií a výběr](../../extensibility/internals/hierarchies-and-selection.md).  
  
|Název třídy|  
|----------------|  
|`Microsoft.VisualStudio.Package.HierarchyNode`|  
|`Microsoft.VisualStudio.Package.ProjectNode`|  
|`Microsoft.VisualStudio.Package.ProjectContainerNode`|  
|`Microsoft.VisualStudio.Package.FileNode`|  
|`Microsoft.VisualStudio.Package.FolderNode`|  
|`Microsoft.VisualStudio.Package.ReferenceContainerNode`|  
|`Microsoft.VisualStudio.Package.ReferenceNode`|  
|`Microsoft.VisualStudio.Package.ProjectReferenceNode`|  
|`Microsoft.VisualStudio.Package.ComReferenceNode`|  
|`Microsoft.VisualStudio.Package.AssemblyReferenceNode`|  
|`Microsoft.VisualStudio.Package.BuildDependency`|  
  
## <a name="document-handling-classes"></a>Třídy zpracování dokumentů  
 Následující tabulka uvádí třídy v MPF, které podporují zpracování dokumentů. Další informace najdete v tématu [otevírání a ukládání položky projektu](../../extensibility/internals/opening-and-saving-project-items.md).  
  
|Název třídy|  
|----------------|  
|`Microsoft.VisualStudio.Package.DocumentManager`|  
|`Microsoft.VisualStudio.Package.FileDocumentManager`|  
  
## <a name="configuration-and-output-classes"></a>Konfigurace a třídy výstupu  
 Následující tabulka uvádí třídy v MPF, která umožní typy projektů podporují více konfigurace, jako je ladění a vydání a kolekce výstupu projektu @. Další informace najdete v tématu [Správa možnosti konfigurace](../../extensibility/internals/managing-configuration-options.md).  
  
|Název třídy|  
|----------------|  
|`Microsoft.VisualStudio.Package.ConfigProvider`|  
|`Microsoft.VisualStudio.Package.ProjectConfig`|  
|`Microsoft.VisualStudio.Package.BuildableProjectConfig`|  
|`Microsoft.VisualStudio.Package.OutputGroup`|  
|`Microsoft.VisualStudio.Package.ProjectElement`|  
  
## <a name="automation-support-classes"></a>Podpora automatizace třídy  
 Následující tabulka uvádí třídy v MPF, které podporují automatizace, tak, aby uživatelé vašeho projektu typu můžete napsat doplňků.  
  
|Název třídy|  
|----------------|  
|`Microsoft.VisualStudio.Package.Automation.OAProject`|  
|`Microsoft.VisualStudio.Package.Automation.OANavigableProjectItems`|  
|`Microsoft.VisualStudio.Package.Automation.OAProjectItems`|  
|`Microsoft.VisualStudio.Package.Automation.OAProjectItem`|  
|`Microsoft.VisualStudio.Package.Automation.OANestedProjectItem`|  
  
## <a name="properties-classes"></a>Vlastnosti třídy  
 V následující tabulce jsou uvedeny třídy v MPF, která umožní typy projektů přidejte vlastnosti uživatele můžete procházet a změnit v prohlížeči vlastností.  
  
|Název třídy|  
|----------------|  
|`Microsoft.VisualStudio.Package.LocalizableProperties`|  
|`Microsoft.VisualStudio.Package.NodeProperties`|  
|`Microsoft.VisualStudio.Package.FileNodeProperties`|  
|`Microsoft.VisualStudio.Package.ProjectNodeProperties`|  
|`Microsoft.VisualStudio.Package.FolderNodeProperties`|  
|`Microsoft.VisualStudio.Package.ReferenceNodeProperties`|