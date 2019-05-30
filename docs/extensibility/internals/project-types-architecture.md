---
title: Architektura typů projektů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], architecture
ms.assetid: 9c1d940f-8a54-41f7-a8aa-c870e324371c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6d77524097509c45c23d6a3d9cc147e5aba6691d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66318899"
---
# <a name="project-types-architecture"></a>Architektura typů projektů
Tato část obsahuje podrobné informace o architektuře typů projektů v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="in-this-section"></a>V tomto oddílu
- [Prvky modelu projektu](../../extensibility/internals/elements-of-a-project-model.md)

 Obsahuje seznam služeb, které můžou využívat typu projektu a, kterou musí implementovat rozhraní.

- [Základní komponenty modelu projektu](../../extensibility/internals/project-model-core-components.md)

 Popisuje rozhraní pro typy projektů musí implementovat i může volitelně implementovat k poskytnutí dalších funkcí.

- [Kdy vytvořit typy projektů](../../extensibility/internals/when-to-create-project-types.md)

 Pomůže vám při rozhodování musíte při vytváření projektu zadejte a kdy můžete použít jiné [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] funkce rozšíření, jako je například rozšíření VSPackages a editory k dosažení stejného cíle.

- [Hierarchie a výběr](../../extensibility/internals/hierarchies-and-selection.md)

 Popisuje, jak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] používá hierarchie a výběr kontextu pro zajištění konzistentní a zjednodušené uživatelské prostředí.

## <a name="related-sections"></a>Související oddíly
- [Podtypy projektů](../../extensibility/internals/project-subtypes.md)

 Vysvětluje, jak podtypů projektů umožňují přizpůsobit chování systémů projektů [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] a [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)].

- [Typy projektů](../../extensibility/internals/project-types.md)

 Poskytuje přehled o projekty jako základní stavební bloky [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE). Jsou uvedeny odkazy na další témata, která popisují, jak řídit projekty vytváření a kompilování kódu.