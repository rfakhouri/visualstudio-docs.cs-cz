---
title: Vývoj služby starší verze jazyka | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- vs.vsip.LangServWiz.langtoks
- vs.vsip.LangServWiz.welcome
- vs.vsip.LangServWiz.langSpec
- vs.vsip.LangServWiz.langInfo
- vs.vsip.LangServWiz.langServOpts
helpviewer_keywords:
- language services, developing
ms.assetid: 6151ba88-c1c3-41de-a1cc-668f494d48d1
caps.latest.revision: 29
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0a4477249dfad57bb75a83b40d6c3b1a4343a23f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54798569"
---
# <a name="developing-a-legacy-language-service"></a>Vývoj služby starší verze jazyka
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Tento oddíl obsahuje odkazy na témata, které umožňují vytvoření služby starší verze jazyka.  
  
 Služby starší verze jazyka jsou implementovány jako součást sady VSPackage, ale novější způsob implementace funkce služba jazyka je pro použití rozšíření MEF. Další informace o nový způsob implementace služby jazyka najdete v tématu [Editor a rozšíření služeb jazyka](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat nový editor API co nejdříve. Tím vylepšíme výkonu vaší služby jazyka a umožňují využívat nové funkce editoru.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Model služby starší verze jazyka](../../extensibility/internals/model-of-a-legacy-language-service.md)  
 Poskytuje služby minimální jazyka pro model [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] základní editor. Tento model jako vodítko můžete použít k vytváření vlastních služeb jazyka.  
  
 [Rozhraní služby starší verze jazyka](../../extensibility/internals/legacy-language-service-interfaces.md)  
 Tento článek popisuje objekty nezbytné k implementaci služby jazyka a poskytuje seznam další objekty, které můžete použít k zajištění zvýrazňování syntaxe, metoda dat a další funkce.  
  
 [Příkazy zachytávání služby starší verze jazyka](../../extensibility/internals/intercepting-legacy-language-service-commands.md)  
 Popisuje, jak vložit příkaz filtru do služby jazyka pro příkazy zachycení, které by jinak zpracovat zobrazení textu.  
  
 [Registrace služby starší verze jazyka](../../extensibility/internals/registering-a-legacy-language-service2.md)  
 Poskytuje informace o tom, jak zaregistrovat vaše služba jazyka pomocí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 [Podpora služby jazyka pro ladění](../../extensibility/internals/language-service-support-for-debugging.md)  
 Popisuje, jak služba jazyka může poskytovat funkce pro podporu ladicího programu.  
  
 [Kontrolní seznam: Vytvoření služby starší verze jazyka](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)  
 Poskytuje podrobné pokyny pro vytváření a integrace language service pro základní editor.  
  
## <a name="related-sections"></a>Související oddíly  
 [Barevné zvýrazňování syntaxe ve službě starší verze jazyka](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Popisuje, jak implementovat, zvýrazňování syntaxe ve vaší službě jazyka.  
  
 [Dokončování příkazů ve službě starší verze jazyka](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)  
 Tento článek popisuje dokončování příkazů, proces, podle kterého služba jazyka pomáhá uživatelům dokončit – klíčové slovo jazyka nebo element, kterou zahájil psát.  
  
 [Informace o parametrech ve službě starší verze jazyka](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)  
 Popisuje, jak získat tipy metodu přetížených funkcí a metod.  
  
 [Postupy: Poskytování podpory skrytého textu ve službě starší verze jazyka](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)  
 Vysvětluje účel oblasti skrytého textu a poskytuje pokyny o tom, jak implementovat oblasti skrytého textu.  
  
 [Postupy: Rozšířená podpora osnovy ve službě starší verze jazyka](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)  
 Vysvětluje dvě možnosti, které rozšiřují podpora osnovy pro váš jazyk nad rámec podpora *sbalit do definic* příkazu.
