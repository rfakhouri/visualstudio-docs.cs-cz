---
title: Zdrojový ovládací prvky návrhu balíčku VSPackage | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control packages, design elements
ms.assetid: edd3f2ff-ca32-4465-8ace-4330493b67bb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9e10825bb9bc9659728fbaaeb023a595745b7bcd
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56642700"
---
# <a name="source-control-vspackage-design-elements"></a>Prvky návrhu balíčku VSPackage správy zdrojového kódu
Témata v této části popisují strukturu, kterou pro těsné integraci se musí implementovat balíčku VSPackage správy zdrojového kódu. Obsahuje také seznam rozhraní a služby, které zdroj správy VSPackage můžete implementovat a rozhraní a služby správy zdrojového kódu VSPackage můžete použít z jiných [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] součásti pro podporu jeho zdrojový ovládací prvek modelu a funkce.

## <a name="in-this-section"></a>V tomto oddílu
- [Struktura balíčku VSPackage](../../extensibility/internals/vspackage-structure-source-control-vspackage.md)

 Definuje strukturu správy zdrojového kódu VSPackage.

- [Související služby a rozhraní](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)

 Obsahuje seznam související balíček rozhraní ovládacího prvku zdroje a služeb.

- [Poskytované služby](../../extensibility/internals/services-provided-source-control-vspackage.md)

 Popisuje službu správy zdrojových kódů poskytuje ovládací prvek zdroje balíčku VSPackage.

## <a name="related-sections"></a>Související oddíly
- [Vytvoření balíčku VSPackage správy zdrojového kódu](../../extensibility/internals/creating-a-source-control-vspackage.md)

 Tento článek popisuje postup vytvoření balíčku VSPackage, který nejen poskytuje funkce správy zdrojového kódu však lze použít k přizpůsobení správy zdrojového kódu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zdrojového ovládacího prvku uživatelského rozhraní.