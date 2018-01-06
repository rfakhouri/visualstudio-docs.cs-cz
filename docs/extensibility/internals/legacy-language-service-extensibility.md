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
ms.workload: vssdk
ms.openlocfilehash: 0cc4913141350b0e0efa65ec0b4db913b578460b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="legacy-language-service-extensibility"></a>Rozšíření služby starší verze jazyka
Služba jazyka poskytuje podporu pro specifický jazyk pro úpravy zdrojového kódu v prostředí IDE.  
  
 Starší verze jazyka služby jsou implementovány jako součást VSPackage, ale novější způsob implementace funkce služby jazyk je použití MEF rozšíření. Další informace o nový způsob implementace služba jazyka, najdete v tématu [Editor a rozšíření služeb jazyk](../../extensibility/editor-and-language-service-extensions.md).  
  
 Tato část popisuje strukturu a implementaci služby starší verze jazyka.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Migrace služby starší verze jazyka](../../extensibility/internals/migrating-a-legacy-language-service.md)  
 Vysvětluje, jak aktualizovat na nejnovější verzi služby jazyk z Visual Studio 2008.  
  
 [Základy služby starší verze jazyka](../../extensibility/internals/legacy-language-service-essentials.md)  
 Poskytuje důležité informace o tom, jak vyvíjet jazyk služby pro integraci programovací jazyk do sady Visual Studio.  
  
 [Vývoj služby starší verze jazyka](../../extensibility/internals/developing-a-legacy-language-service.md)  
 Obsahuje odkazy na témata, která vám pomůžou vytvořit služba jazyka.  
  
 [Barevné zvýrazňování syntaxe ve službě starší verze jazyka](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Poskytuje informace o podpoře zvýraznění syntaxe v služba jazyka.  
  
 [Implementace služby jazyk starší verze](../../extensibility/internals/implementing-a-legacy-language-service1.md)  
 Poskytuje informace o tom, jak použít rozhraní spravované balíčku (MPF) k implementaci služby plnohodnotný jazyk ve spravovaném kódu.  
  
 [Podpůrné nástroje procházení symbolů](../../extensibility/internals/supporting-symbol-browsing-tools.md)  
 Popisuje knihovny a nástroje, které umožňují procházet stromové zobrazení symbolů v prostředí IDE.  
  
## <a name="related-sections"></a>Související oddíly  
 [Editor a rozšíření služeb jazyka](../../extensibility/editor-and-language-service-extensions.md)  
 Poskytuje přehled editory Visual Studio.  
  
 [Podpora služby jazyka pro ladění](../../extensibility/internals/language-service-support-for-debugging.md)  
 Poskytuje informace o a odkaz k sadě Visual Studio ladění SDK, která obsahuje informace, které je potřeba vytvářet a přizpůsobovat ladicí program komponenty používané k ladění programů.