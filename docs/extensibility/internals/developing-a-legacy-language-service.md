---
title: Vývoj starší verze služby jazyk | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6cf384a22429c6314bf5e2fcbb66db7974d42c87
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="developing-a-legacy-language-service"></a>Vývoj služby jazyk starší verze
Tento oddíl obsahuje odkazy na témata, které vám pomůžou vytvořit službu starší verze jazyka.  
  
 Starší verze jazyka služby jsou implementovány jako součást VSPackage, ale novější způsob implementace funkce služby jazyk je použití MEF rozšíření. Další informace o nový způsob implementace služba jazyka, najdete v tématu [Editor a rozšíření služeb jazyk](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat co nejdříve editoru nové rozhraní API. Tím zvýšit výkon služby jazyk a umožňují využívat výhod nových funkcí editoru.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Model služby starší verze jazyka](../../extensibility/internals/model-of-a-legacy-language-service.md)  
 Poskytuje služby minimální jazyk pro model [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] základní editor. Tento model jako vodítko můžete použít pro vytvoření služby jazyk.  
  
 [Rozhraní služby starší verze jazyka](../../extensibility/internals/legacy-language-service-interfaces.md)  
 Popisuje objekty nezbytné k implementaci jazykové služby a poskytuje seznam další objekty, které můžete použít k zajištění zvýraznění syntaxe, metoda dat a dalších funkcí.  
  
 [Příkazy zachytávání služby starší verze jazyka](../../extensibility/internals/intercepting-legacy-language-service-commands.md)  
 Popisuje, jak vložení příkaz filtru do služby jazyk intercept příkazy, které by jinak zpracovat textového zobrazení.  
  
 [Registrace služby jazyk starší verze](../../extensibility/internals/registering-a-legacy-language-service2.md)  
 Poskytuje informace o tom, jak zaregistrovat jazykové služby pomocí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Podpora služby jazyka pro ladění](../../extensibility/internals/language-service-support-for-debugging.md)  
 Popisuje, jak služba jazyka může poskytovat funkce pro podporu ladicí program.  
  
 [Kontrolní seznam: Vytvoření služby starší verze jazyka](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)  
 Poskytuje podrobné pokyny pro vytváření a integrace služba jazyka pro editor jádra.  
  
## <a name="related-sections"></a>Související oddíly  
 [Barevné zvýrazňování syntaxe ve službě starší verze jazyka](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Popisuje, jak implementovat zvýraznění syntaxe ve službě jazyk.  
  
 [Dokončování příkazů ve službě starší verze jazyka](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)  
 Popisuje dokončování příkazů, proces, pomocí kterého služba jazyka pomáhá uživatelům dokončit klíčové slovo jazyka nebo element, který zahájil zadáním.  
  
 [Informace o parametrech ve službě jazyk starší verze](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)  
 Popisuje, jak zajistit metoda tipy pro přetížené funkce a metody.  
  
 [Postupy: Poskytování podpory skrytého textu ve službě starší verze jazyka](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)  
 Vysvětlující účel oblast skrytého textu a poskytuje pokyny o tom, jak implementovat oblast skrytého textu.  
  
 [Postupy: Rozšířená podpora osnovy ve službě starší verze jazyka](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)  
 Popisuje dvě možnosti, které rozšiřují popisující podporu pro svůj jazyk nad rámec podpora *sbalit do definice* příkaz.