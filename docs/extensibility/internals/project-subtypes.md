---
title: "Projekt podtypů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], subtypes
- project subtypes [Visual Studio SDK]
ms.assetid: d235b47b-cf11-4d47-a63f-e33d9d16105d
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 84d2700e1dfb5d66fb2df6376db9e0ce5352ad4e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="project-subtypes"></a>Projekt podtypů
Projekt podtypů umožňují přizpůsobit nebo flavor chování projektu systémech [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Přizpůsobení zahrnují ukládání další data v souboru projektu, přidání nebo filtrování položek v **přidat novou položku** dialogové okno, řízení jakým způsobem jsou sestavení ladit a nasadit a rozšíření projektu **vlastnost Stránky** dialogové okno. VSPackages implementovat podtypů projektu pomocí COM agregace.  
  
> [!NOTE]
>  Systém projektu Visual C++ nepodporuje podtypů projektu. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]samotný podtypů projektu používá k implementaci projekty pro inteligentní zařízení a systému SQL Server.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Návrh podtypů projektu](../../extensibility/internals/project-subtypes-design.md)  
 Popisuje koncept podtypů projektu.  
  
 [Pořadí inicializace podtypů projektu](../../extensibility/internals/initialization-sequence-of-project-subtypes.md)  
 Popisuje pořadí inicializace dílčí programový projektu pomocí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí.  
  
 [Vlastnosti a metody prodloužena podtypů projektu](../../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)  
 Poskytuje podrobný popis funkce a metody, které jsou nejčastěji rozšířeno pomocí podtypů projektu.  
  
 [Zachování dat v souboru projektu nástroje MSBuild](../../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)  
 Popisuje, jak uchovávat data v souboru projektu a jak používat <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> zachování dat v souboru projektu na úrovni projektu dílčí agregace.  
  
 [Projekt vlastnost uživatelské rozhraní](../../extensibility/internals/project-property-user-interface.md)  
 Popisuje, jak podtypů projektu můžete upravit projektu **stránky vlastností** dialogové okno.  
  
 [Rozšíření objektový Model základní projektu](../../extensibility/internals/extending-the-object-model-of-the-base-project.md)  
 Poskytuje informace o jak projektu podtypů automatizace Extender k rozšíření můžete použít objektový model automatizace.  
  
 [Které přispívají k informacím přidat novou položku – dialogové okno](../../extensibility/internals/contributing-to-the-add-new-item-dialog-box.md)  
 Popisuje postup přidání položky do **přidat novou položku** dialogové okno.  
  
 [Ukládání dat v souborech projektu](../../extensibility/saving-data-in-project-files.md)  
 Vysvětluje, jak uložit a načtení dat specifické pro podtyp v souboru projektu pomocí spravované balíček Framework (MPF) podtypem projektu.  
  
 [Zpracování specializuje nasazení](../../extensibility/internals/handling-specialized-deployment.md)  
 Vysvětluje, jak můžete zadat chování specializovaná nasazení implementací podtypů projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> rozhraní.  
  
 [Přidávání a odebírání stránky vlastností](../../extensibility/adding-and-removing-property-pages.md)  
 Popisuje přidání a odebrání stránky vlastností v Návrháři projektu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Typy projektů](../../extensibility/internals/project-types.md)  
 Obsahuje odkazy na témata s podrobnostmi o [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projekty.