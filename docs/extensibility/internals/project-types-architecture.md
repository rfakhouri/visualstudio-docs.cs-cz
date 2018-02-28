---
title: Typy projektu architektura | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], architecture
ms.assetid: 9c1d940f-8a54-41f7-a8aa-c870e324371c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 34402ae0b998d4ae534507e23ffa31e0d7cef9bb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="project-types-architecture"></a>Architektura typy projektu
Tato část obsahuje podrobné informace o architektuře typy projektů v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Prvky modelu projektu](../../extensibility/internals/elements-of-a-project-model.md)  
 Jsou uvedené služby, které můžou využívat typu projektu a, kterou musí implementovat rozhraní.  
  
 [Základní komponenty modelu projektu](../../extensibility/internals/project-model-core-components.md)  
 Popisuje rozhraní typy projektů současně musí implementovat a volitelně můžete implementovat dodatečných funkcí.  
  
 [Kdy vytvořit typy projektů](../../extensibility/internals/when-to-create-project-types.md)  
 Zadejte pomůže vám při rozhodování při musíte vytvořit projekt a kdy můžete použít jiné [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] funkce rozšíření, jako je například VSPackages a editory k dosažení stejného cíle.  
  
 [Hierarchie a výběr](../../extensibility/internals/hierarchies-and-selection.md)  
 Popisuje, jak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] používá hierarchie a výběr kontextu zajistit konzistentní a zjednodušená uživatelské prostředí.  
  
## <a name="related-sections"></a>Související oddíly  
 [Podtypy projektů](../../extensibility/internals/project-subtypes.md)  
 Vysvětluje, jak projektu podtypů umožňují přizpůsobit chování projektu systémy [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] a [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)].  
  
 [Typy projektů](../../extensibility/internals/project-types.md)  
 Poskytuje přehled projekty jako základní stavební bloky [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE). Jsou uvedeny odkazy na další témata, které vysvětlují, jak řídit projekty vytváření a kompilování kódu.