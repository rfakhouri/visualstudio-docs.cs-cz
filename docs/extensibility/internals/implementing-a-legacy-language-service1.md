---
title: "Implementace starší verze jazyka Service1 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: language services, managed
ms.assetid: df638f24-166d-4b80-be82-c9c39ca7a556
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 304d99c1ddd5fdfddba0c4df88fc4eeeb9dcb7ac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-a-legacy-language-service"></a>Implementace služby jazyk starší verze
Třídy v rámci spravované balíčku (MPF) můžete použít k implementaci starší verze jazyka služba, která podporuje širokou řadu funkcí, například zvýraznění syntaxe, odpovídající složené závorce a doplňování IntelliSense.  
  
 Starší verze jazyka služby jsou implementovány jako součást VSPackage, ale novější způsob implementace funkce služby jazyk je použití MEF rozšíření. Další informace o nový způsob implementace služba jazyka, najdete v tématu [Editor a rozšíření služeb jazyk](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat co nejdříve editoru nové rozhraní API. Tím zvýšit výkon služby jazyk a umožňují využívat výhod nových funkcí editoru.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přehled služby starší verze jazyka](../../extensibility/internals/legacy-language-service-overview.md)  
 Přehled funkcí služby jazyka, které jsou podporovány v MPF.  
  
 [Implementace služby jazyk starší verze](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
 Popisuje, co je potřeba k implementaci a použití sady MPF služba jazyka.  
  
 [Registrace služby jazyk starší verze](../../extensibility/internals/registering-a-legacy-language-service1.md)  
 Popisuje kroky, které jsou potřeba k registraci služby jazyk na základě sady MPF s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Analyzátor a skener služby starší verze jazyka](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)  
 Popisuje dvě analyzátory, které jsou nutné k implementaci všech funkcí jazyka služby pomocí MPF.  
  
 [Návod: Vytvoření služby starší verze jazyka](../../extensibility/internals/walkthrough-creating-a-legacy-language-service.md)  
 Poskytuje základní kroky, které jsou nutné k implementaci služby jazykové sady MPF ve VSPackage.  
  
 [Návod: Získání seznamu nainstalovaných fragmentů kódu (implementace starší verze)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)  
 Ukazuje techniky načítání seznamu fragmenty kódu nainstalované.  
  
 [Funkce služby starší verze jazyka](../../extensibility/internals/legacy-language-service-features1.md)  
 Obsahuje odkazy na témata týkající se této podrobností, co je třeba provést pomocí sady MPF implementovat všechny funkce služba jazyka.