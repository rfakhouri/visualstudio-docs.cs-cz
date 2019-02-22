---
title: Podtypy projektů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], subtypes
- project subtypes [Visual Studio SDK]
ms.assetid: d235b47b-cf11-4d47-a63f-e33d9d16105d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 027dc559c33b5b8f10a4555985e8b2a5a5a416c5
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604935"
---
# <a name="project-subtypes"></a>Podtypy projektů
Podtypy projektů vám umožní přizpůsobit nebo flavor chování systémů projektů [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Vlastní nastavení zahrnují ukládá další data v souboru projektu, přidání nebo filtrování položek v **přidat novou položku** dialogové okno, řízení, jak ladit a nasadit, sestavení a rozšíření projektu **vlastnost Stránky** dialogové okno. Rozšíření VSPackages implementovat podtypů projektů pomocí modelu COM agregace.

> [!NOTE]
>  Systém projektu Visual C++ nepodporuje podtypů projektů. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] samotný podtypů projektů používá k implementaci projekty systému SQL Server a inteligentní zařízení.

## <a name="in-this-section"></a>V tomto oddílu
- [Návrh podtypů projektů](../../extensibility/internals/project-subtypes-design.md)

 Popisuje pojem podtypů projektů.

- [Inicializační sekvence podtypů projektů](../../extensibility/internals/initialization-sequence-of-project-subtypes.md)

 Popisuje pořadí inicializace podtyp projektu programový podle [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí.

- [Vlastnosti a metody rozšířené prostřednictvím podtypů projektů](../../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)

 Poskytuje podrobný popis funkce a metody nejčastěji rozšířené prostřednictvím podtypů projektů.

- [Trvalá data v souboru projektu nástroje MSBuild](../../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)

 Popisuje, jak zachovat data v souboru projektu a jak používat <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> zachovat data v souboru projektu úrovních agregace podtyp projektu.

- [Uživatelské rozhraní vlastností projektu](../../extensibility/internals/project-property-user-interface.md)

 Popisuje, jak podtypů projektů můžete upravit projekt **stránky vlastností** dialogové okno.

- [Rozšíření objektového modelu základního projektu](../../extensibility/internals/extending-the-object-model-of-the-base-project.md)

 Poskytuje informace o jak podtypů projektů můžete použít zařízení Extender automatizace k rozšíření objektového modelu automatizace.

- [Přispívání do dialogového okna Přidat novou položku](../../extensibility/internals/contributing-to-the-add-new-item-dialog-box.md)

 Popisuje postup přidání položky, které chcete **přidat novou položku** dialogové okno.

- [Ukládání dat v souborech projektu](../../extensibility/saving-data-in-project-files.md)

 Vysvětluje, jak uložit a načíst data specifická pro podtyp v souboru projektu pomocí Managed Package Framework (MPF) podtyp projektu.

- [Zpracování specializovaného nasazení](../../extensibility/internals/handling-specialized-deployment.md)

 Vysvětluje, jak můžete zadat chování specializovaného nasazení implementací podtypů projektů <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> rozhraní.

- [Přidávání a odebírání stránek vlastností](../../extensibility/adding-and-removing-property-pages.md)

 Popisuje, přidávání a odebírání stránek vlastností v Návrháři projektu.

## <a name="related-sections"></a>Související oddíly
- [Typy projektů](../../extensibility/internals/project-types.md)

 Obsahuje odkazy na témata s podrobnostmi o [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projekty.