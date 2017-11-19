---
title: "Vývoj starší verze služby jazyk | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.vsip.LangServWiz.langtoks
- vs.vsip.LangServWiz.welcome
- vs.vsip.LangServWiz.langSpec
- vs.vsip.LangServWiz.langInfo
- vs.vsip.LangServWiz.langServOpts
helpviewer_keywords: language services, developing
ms.assetid: 6151ba88-c1c3-41de-a1cc-668f494d48d1
caps.latest.revision: "28"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e05fb3f0a33c0f033733c40b17d636243c18ee22
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="developing-a-legacy-language-service"></a>Vývoj služby jazyk starší verze
Tento oddíl obsahuje odkazy na témata, které vám pomůžou vytvořit službu starší verze jazyka.  
  
 Starší verze jazyka služby jsou implementovány jako součást VSPackage, ale novější způsob implementace funkce služby jazyk je použití MEF rozšíření. Další informace o nový způsob implementace služba jazyka, najdete v tématu [Editor a rozšíření služeb jazyk](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat co nejdříve editoru nové rozhraní API. Tím zvýšit výkon služby jazyk a umožňují využívat výhod nových funkcí editoru.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Model služby jazyk starší verze](../../extensibility/internals/model-of-a-legacy-language-service.md)  
 Poskytuje služby minimální jazyk pro model [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] základní editor. Tento model jako vodítko můžete použít pro vytvoření služby jazyk.  
  
 [Rozhraní služeb starší verze jazyka](../../extensibility/internals/legacy-language-service-interfaces.md)  
 Popisuje objekty nezbytné k implementaci jazykové služby a poskytuje seznam další objekty, které můžete použít k zajištění zvýraznění syntaxe, metoda dat a dalších funkcí.  
  
 [Brání starší verze jazyka služby příkazy](../../extensibility/internals/intercepting-legacy-language-service-commands.md)  
 Popisuje, jak vložení příkaz filtru do služby jazyk intercept příkazy, které by jinak zpracovat textového zobrazení.  
  
 [Registrace služby jazyk starší verze](../../extensibility/internals/registering-a-legacy-language-service2.md)  
 Poskytuje informace o tom, jak zaregistrovat jazykové služby pomocí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Jazyková podpora služby pro ladění](../../extensibility/internals/language-service-support-for-debugging.md)  
 Popisuje, jak služba jazyka může poskytovat funkce pro podporu ladicí program.  
  
 [Kontrolní seznam: Vytvoření služby jazyk starší verze](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)  
 Poskytuje podrobné pokyny pro vytváření a integrace služba jazyka pro editor jádra.  
  
## <a name="related-sections"></a>Související oddíly  
 [Ve službě jazyk starší zvýrazňování syntaxe](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Popisuje, jak implementovat zvýraznění syntaxe ve službě jazyk.  
  
 [Dokončování příkazů ve službě jazyk starší verze](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)  
 Popisuje dokončování příkazů, proces, pomocí kterého služba jazyka pomáhá uživatelům dokončit klíčové slovo jazyka nebo element, který zahájil zadáním.  
  
 [Informace o parametrech ve službě jazyk starší verze](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)  
 Popisuje, jak zajistit metoda tipy pro přetížené funkce a metody.  
  
 [Postupy: podporují skrytého textu ve službě jazyk starší verze](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)  
 Vysvětlující účel oblast skrytého textu a poskytuje pokyny o tom, jak implementovat oblast skrytého textu.  
  
 [Postupy: podporují rozšířené popisující ve službě jazyk starší verze](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)  
 Popisuje dvě možnosti, které rozšiřují popisující podporu pro svůj jazyk nad rámec podpora *sbalit do definice* příkaz.