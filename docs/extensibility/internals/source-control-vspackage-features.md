---
title: Funkce balíčku VSPackage správy zdrojového | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control packages, features
ms.assetid: 26c3ffda-22b8-4345-9fb6-2883f37699aa
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 513f43787040075ea0904c97b1aca9866359520a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66322497"
---
# <a name="source-control-vspackage-features"></a>Funkce balíčku VSPackage správy zdrojového kódu
Tato část popisuje různé funkce balíčku VSPackage správy zdrojového kódu. Popisuje registraci a výběr podrobností pro tyto VSPackage a popisuje tři hlavní zdroje funkce související s ovládacími: zpracování událostí dotazu upravit dotaz uložit (QEQS), nahrazení piktogram a vlastní uživatelské rozhraní (UI) pro správu zdrojového kódu funkce.

## <a name="in-this-section"></a>V tomto oddílu
- [Registrace a výběr](../../extensibility/internals/registration-and-selection-source-control-vspackage.md)

 Popisuje mechanismy registrace a výběr balíčků.

- [Události QEQS (Query Edit Query Save)](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md)

 Vysvětluje roli dotaz upravit dotaz ukládání událostí a jak jsou zpracovány správy zdrojového kódu VSPackage.

- [Správa piktogramů](../../extensibility/internals/glyph-control-source-control-vspackage.md)

 Popisuje úrovně piktogramů a způsobu jejich implementace.

- [Vlastní uživatelského rozhraní](../../extensibility/internals/custom-user-interface-source-control-vspackage.md)

 Popisuje prvky uživatelského rozhraní, které můžete zadat balíčku VSPackage správy zdrojového kódu.

## <a name="related-sections"></a>Související oddíly
- [Vytvoření balíčku VSPackage správy zdrojového kódu](../../extensibility/internals/creating-a-source-control-vspackage.md)

 Tento článek popisuje postup vytvoření balíčku VSPackage, který nejen poskytuje funkce správy zdrojového kódu však lze použít k přizpůsobení správy zdrojového kódu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zdrojového ovládacího prvku uživatelského rozhraní.