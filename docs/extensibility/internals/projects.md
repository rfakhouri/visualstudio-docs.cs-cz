---
title: Projekty | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- solutions [Visual Studio]
- custom tools [Visual Studio SDK]
- project subtypes [Visual Studio SDK]
- projects [Visual Studio SDK]
- project types [Visual Studio SDK]
ms.assetid: 237742e4-a638-4d5b-a9b3-6a69d627763c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0ae786d3fa65bdf4ce591be1c8ec677a5ac757e7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56615530"
---
# <a name="projects"></a>Projekty
V sadě Visual Studio jsou projekty kontejnery, které vývojáři použít k uspořádání souborů zdrojového kódu a další prostředky, které se zobrazují v **Průzkumníka řešení**. Projekty jsou obvykle soubory (například soubor .csproj projektu v jazyce C#), které ukládají odkazy na soubory se zdrojovým kódem a prostředky jako rastrové soubory. Projekty umožňují organizovat, vytváření, ladění a nasazení zdrojového kódu, odkazy na webové služby a databáze a další prostředky. Rozšíření VSPackages můžete rozšířit systém projektu sady Visual Studio třemi hlavními způsoby: *typy projektů*, *podtypů projektu*, a *vlastních nástrojů*.

## <a name="in-this-section"></a>V tomto oddílu
- [Typy projektů](../../extensibility/internals/project-types.md)

 *Typy projektů* přidat podporu pro nové typy projektů, jako je například programovacích jazyků. Například každý jazyk, který podporuje Visual Studio má svůj vlastní typ projektu a ukázka integrace IronPython zahrnuje typ projektu jazyka Ironpythonu. Je nutné vytvořit typ projektu pro jiné jazyky než C# nebo Visual Basic k přizpůsobení, jak jsou položky vytvořené, ladění, nasazení a zobrazí v **Průzkumníka řešení**. Další informace najdete v tématu [typy projektů](../../extensibility/internals/project-types.md).

- [Podtypy projektů](../../extensibility/internals/project-subtypes.md)

 *Podtypy projektů* jsou založeny na typech projektů a slouží k úpravám způsobu vytvořené, ladit a nasadit projekty. Visual Studio používá s projekty Smart Device; podtypů projektů nasazení se přizpůsobit zkopírováním program nově vytvořené z vývojového počítače na cílovém zařízení. C# a typy projektů jazyka Visual Basic můžete použít jako základ pro podtypy projektů; Nelze provést typy projektů jazyka C++. Vlastní typy projektů lze také použít jako základ pro podtypy projektů. Další informace najdete v tématu [podtypů projektů](../../extensibility/internals/project-subtypes.md).

- [Webové projekty](../../extensibility/internals/web-projects.md)

 Vysvětluje webový projekt, který zase vytvářet webové aplikace.

- [Nová generace projektů: Pod pokličkou, část 1](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md) a [nová generace projektů: Pod pokličkou část 2](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)

 Vysvětluje, co se ve skutečnosti stane při vytvoření nového projektu.

- [Ukázky VSSDK](http://aka.ms/vs2015sdksamples) obsahuje ukázky VSSDK, které pracují s projekty a řešení.

## <a name="related-sections"></a>Související oddíly
- [Práce se sadou Visual Studio SDK](../../extensibility/internals/inside-the-visual-studio-sdk.md)

 Popisují různé aspekty rozšiřitelnost sady Visual Studio.