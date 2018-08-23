---
title: Projekty | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- solutions [Visual Studio]
- custom tools [Visual Studio SDK]
- project subtypes [Visual Studio SDK]
- projects [Visual Studio SDK]
- project types [Visual Studio SDK]
ms.assetid: 237742e4-a638-4d5b-a9b3-6a69d627763c
caps.latest.revision: 44
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ade0234423c907c675bc1dd53e3436dfa38ca26e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628854"
---
# <a name="projects"></a>Projekty
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [projekty](https://docs.microsoft.com/visualstudio/extensibility/internals/projects).  
  
V sadě Visual Studio jsou projekty kontejnery, které vývojáři použít k uspořádání souborů zdrojového kódu a další prostředky, které se zobrazují v **Průzkumníka řešení**. Projekty jsou obvykle soubory (například soubor .csproj projektu v jazyce C#), které ukládají odkazy na soubory se zdrojovým kódem a prostředky jako rastrové soubory. Projekty umožňují organizovat, vytváření, ladění a nasazení zdrojového kódu, odkazy na webové služby a databáze a další prostředky. Rozšíření VSPackages můžete rozšířit systém projektu sady Visual Studio třemi hlavními způsoby: *typy projektů*, *podtypů projektu*, a *vlastních nástrojů*.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Typy projektů](../../extensibility/internals/project-types.md)  
 *Typy projektů* přidat podporu pro nové typy projektů, jako je například programovacích jazyků. Například každý jazyk, který podporuje Visual Studio má svůj vlastní typ projektu a ukázka integrace IronPython zahrnuje typ projektu jazyka Ironpythonu. Je nutné vytvořit typ projektu pro jiné jazyky než C# nebo Visual Basic k přizpůsobení, jak jsou položky vytvořené, ladění, nasazení a zobrazí v **Průzkumníka řešení**. Další informace najdete v tématu [typy projektů](../../extensibility/internals/project-types.md).  
  
 [Podtypy projektů](../../extensibility/internals/project-subtypes.md)  
 *Podtypy projektů* jsou založeny na typech projektů a slouží k úpravám způsobu vytvořené, ladit a nasadit projekty. Visual Studio používá s projekty Smart Device; podtypů projektů nasazení se přizpůsobit zkopírováním program nově vytvořené z vývojového počítače na cílovém zařízení. C# a typy projektů jazyka Visual Basic můžete použít jako základ pro podtypy projektů; Nelze provést typy projektů jazyka C++. Vlastní typy projektů lze také použít jako základ pro podtypy projektů. Další informace najdete v tématu [podtypů projektů](../../extensibility/internals/project-subtypes.md).  
  
 [Webové projekty](../../extensibility/internals/web-projects.md)  
 Vysvětluje webový projekt, který zase vytvářet webové aplikace.  
  
 [Nová generace projektů: Pod pokličkou, část 1](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md) a [nová generace projektů: pod pokličkou, část 2](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)  
 Vysvětluje, co se ve skutečnosti stane při vytvoření nového projektu.  
  
 [Ukázky VSSDK](../../misc/vssdk-samples.md)  
 Popisuje ukázky VSSDK, které pracují s projekty a řešení.  
  
## <a name="related-sections"></a>Související oddíly  
 [Práce se sadou Visual Studio SDK](../../extensibility/internals/inside-the-visual-studio-sdk.md)  
 Popisují různé aspekty rozšiřitelnost sady Visual Studio.

