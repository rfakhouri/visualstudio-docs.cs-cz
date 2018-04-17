---
title: Starší verze jazyka služby Essentials | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- languages, integrating into Visual Studio
- language services, integrating programming languages
- Visual Studio, integrating programming languages
- programming languages, integrating into Visual Studio
ms.assetid: c15e0ccb-e7c5-4dbb-affb-fe3d3244debe
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 68b92b821ad77b050ad2116da6fd930b975dad5a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="legacy-language-service-essentials"></a>Starší verze jazyka služby Essentials
Je nutné zadat služba jazyka pro integraci programovací jazyk do sady Visual Studio. Toto téma popisuje funkce dostupné v starší verze jazykových služeb.  
  
 Starší verze jazyka služby jsou implementovány jako součást VSPackage, ale novější způsob implementace funkce služby jazyk je použití MEF rozšíření. Další informace o nový způsob implementace služba jazyka, najdete v tématu [Editor a rozšíření služeb jazyk](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat co nejdříve editoru nové rozhraní API. Tím zvýšit výkon služby jazyk a umožňují využívat výhod nových funkcí editoru.  
  
 Starší verze jazyka služby poskytují následující funkce:  
  
|Funkce|Popis|  
|-------------|-----------------|  
|Barevné zvýrazňování syntaxe|Způsobí, že editor zobrazení jiné barvy a styly písem pro různé elementy jazyka. Tento rozdíl lze usnadňují číst a upravovat soubory.<br /><br /> Obecné informace najdete v tématu [barevné zvýraznění syntaxe ve službě jazyk starší](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md).<br /><br /> Informace o této funkci v rámci spravované balíčku (MPF) najdete v tématu [syntaxe barevné ve službě jazyk starší](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md).|  
|Dokončování příkazů|Dokončení příkazu nebo klíčové slovo, které uživatel bylo zahájeno zadáním. Dokončování pomáhá uživatelům snadno, zadejte obtížné příkazy s menší zadáním a méně šance došlo k chybě.<br /><br /> Obecné informace najdete v tématu [dokončování ve službě jazyk starší](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md).<br /><br /> Informace o této funkci v MPF najdete v tématu [dokončení slova ve službě jazyk starší](../../extensibility/internals/word-completion-in-a-legacy-language-service.md).|  
|Související závorky|Označuje spárován znaky, jako jsou složené závorky. Když uživatel zadá ukončovací znak, jako "}", odpovídající složené závorce klade důraz odpovídající počáteční znak, jako například "{". Po uzavření znaků několik úrovní se tato funkce pomáhá uživatelům potvrďte, že jsou správně spárovat nadřazených znaky.<br /><br /> Informace o této funkci v MPF najdete v tématu [odpovídající složené závorce ve službě jazyk starší](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md).|  
|Informace o parametru popisy tlačítek|Zobrazí seznam možných podpisy pro přetížené metody, které je aktuálně zadání uživatele.<br /><br /> Obecné informace najdete v tématu [informace o parametrech ve službě jazyk starší](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md).<br /><br /> Informace o této funkci v MPF najdete v tématu [informace o parametrech ve službě jazyk starší](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md).|  
|Chyba značky|Zobrazí červenou vlnovkou, také známé jako vlnovkou, v části text, který není syntakticky správný. Chyba značky se obvykle používají, aby uživatele vědět překlepu klíčová slova, uzavřené závorky, neplatné znaky a podobnými chybami.<br /><br /> Do tříd sady MPF chyba značky jsou zpracovávány automaticky v <xref:Microsoft.VisualStudio.Package.AuthoringSink.AddError%2A> metodu <xref:Microsoft.VisualStudio.Package.AuthoringSink> třídy.|  
  
 Mnoho z těchto funkcí vyžaduje služba jazyka analyzovat zdrojového kódu. Často můžete opakovaně použít tokenizaci a analýzy kódu pro kompilátoru nebo překladač.  
  
 Následující funkce se vztahují k podporované programovací jazyky, ale nejsou součástí služby jazyka:  
  
|Funkce|Popis|  
|-------------|-----------------|  
|Vyhodnocovače výrazů|Podporuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladicí program ověřování zarážky a poskytnutím seznam výrazů má být zobrazen v **automobily** okno ladění.<br /><br /> Další informace najdete v tématu [jazyková podpora služby pro ladění](../../extensibility/internals/language-service-support-for-debugging.md).|  
|Symbol procházení nástroje|Podporuje **objektu prohlížeče**, **třídy zobrazení**, **volání prohlížeče**, a **najít Symbol výsledky**.|