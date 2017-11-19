---
title: "Rozšíření služby starší verze jazyka | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language services
- Visual Studio, language services
ms.assetid: 2700cd4d-5f68-43fc-b62f-dc80c3f3aa85
caps.latest.revision: "42"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a5072aef90e08d645bff2a1bb6800e409e7d2104
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="legacy-language-service-extensibility"></a>Rozšíření služby starší verze jazyka
Služba jazyka poskytuje podporu pro specifický jazyk pro úpravy zdrojového kódu v prostředí IDE.  
  
 Starší verze jazyka služby jsou implementovány jako součást VSPackage, ale novější způsob implementace funkce služby jazyk je použití MEF rozšíření. Další informace o nový způsob implementace služba jazyka, najdete v tématu [Editor a rozšíření služeb jazyk](../../extensibility/editor-and-language-service-extensions.md).  
  
 Tato část popisuje strukturu a implementaci služby starší verze jazyka.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Migrace služby jazyk starší verze](../../extensibility/internals/migrating-a-legacy-language-service.md)  
 Vysvětluje, jak aktualizovat na nejnovější verzi služby jazyk z Visual Studio 2008.  
  
 [Starší verze jazyka služby Essentials](../../extensibility/internals/legacy-language-service-essentials.md)  
 Poskytuje důležité informace o tom, jak vyvíjet jazyk služby pro integraci programovací jazyk do sady Visual Studio.  
  
 [Vývoj služby jazyk starší verze](../../extensibility/internals/developing-a-legacy-language-service.md)  
 Obsahuje odkazy na témata, která vám pomůžou vytvořit služba jazyka.  
  
 [Ve službě jazyk starší zvýrazňování syntaxe](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Poskytuje informace o podpoře zvýraznění syntaxe v služba jazyka.  
  
 [Implementace služby jazyk starší verze](../../extensibility/internals/implementing-a-legacy-language-service1.md)  
 Poskytuje informace o tom, jak použít rozhraní spravované balíčku (MPF) k implementaci služby plnohodnotný jazyk ve spravovaném kódu.  
  
 [Podpůrné nástroje procházení – Symbol](../../extensibility/internals/supporting-symbol-browsing-tools.md)  
 Popisuje knihovny a nástroje, které umožňují procházet stromové zobrazení symbolů v prostředí IDE.  
  
## <a name="related-sections"></a>Související oddíly  
 [Editor a rozšíření služeb jazyk](../../extensibility/editor-and-language-service-extensions.md)  
 Poskytuje přehled editory Visual Studio.  
  
 [Jazyková podpora služby pro ladění](../../extensibility/internals/language-service-support-for-debugging.md)  
 Poskytuje informace o a odkaz k sadě Visual Studio ladění SDK, která obsahuje informace, které je potřeba vytvářet a přizpůsobovat ladicí program komponenty používané k ladění programů.