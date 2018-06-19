---
title: Rozšiřitelnost ladicího programu sady Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], Debugging SDK
- Debugging SDK
ms.assetid: c088b6a2-c3ad-446b-830d-9c6f41b2934b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e5bb01c093fda068dfbc7dfa705914a8bdef4d2b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127067"
---
# <a name="visual-studio-debugger-extensibility"></a>Rozšiřitelnost ladicího programu sady Visual Studio
Visual Studio obsahuje ladicí program kód plně interaktivní zdroje, poskytuje efektivní a snadno použitelný nástroj pro sledování dolů chyby v programu. Ladicí program má úplnou podporu jazyka Visual Basic, C#, C/C++ a JavaScript. Nicméně s [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], která je k dispozici z [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=214453), jinými programovací jazyky může být podporovaný v ladicím programu s stejné bohaté funkce.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Ladicí program má ladění součásti, které se v vypnout, specifické pro jazyk laděné běžné front-endu (tedy uživatelského rozhraní). Pro nové jazyky, všechny, které je nezbytné pro podporu pomocí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladicí program je vytvoření komponenty potřebné back-end, jako je například modul ladění (DE). Který je tam, kde [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] odeslán.  
  
 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Zahrnuje úplný odkaz na všechny [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] elementy, které jsou potřebné pro vytvoření nové DE. Kromě toho existují ukázky a výukové programy, které vám pomůžou vám pomůžou začít.  
  
 Ukázka začátku do konce systému jazyk projektu s laděním podpory, najdete v článku [IronPython ukázka](http://msdn.microsoft.com/en-us/4c41695c-12c1-4670-b43b-d8d84c9e4089).  
  
 Následující části popisují, jak rozšířit pomocí ladicího programu [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)].  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)  
 Popisuje, co [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění nabídky a jak nainstalovat sadu SDK.  
  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Dokumenty vlastní proces DE, od přípravy vašeho programu pro DE k odpojení DE.  
  
 [Zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
 Vysvětluje, zda je nutné napsat vyhodnocovací filtr výrazů.  
  
 [Výběr strategie implementace ladicího stroje](../../extensibility/debugger/choosing-a-debug-engine-implementation-strategy.md)  
 Popisuje, jak implementovat vaše DE.  
  
 [Referenční informace](../../extensibility/debugger/reference/reference-visual-studio-debugging-apis.md)  
 Dokumenty [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] rozhraní API pro ladění.  
  
 [Ukázky](../../extensibility/debugger/visual-studio-debugging-samples.md)  
 Obsahuje odkazy na běžné výraz vyhodnocování vzorku runtime jazyka a ukázku modul ladění.
