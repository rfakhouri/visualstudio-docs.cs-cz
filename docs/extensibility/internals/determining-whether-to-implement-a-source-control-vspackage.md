---
title: Určení, jestli se má implementovat VSPackage zdrojového ovládacího prvku | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control packages, about source control packages
ms.assetid: 60b3326e-e7e2-4729-95fc-b682e7ad5c99
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ba0ac240c8b8a93b6afbf1ec7dd580090ee54fd9
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351610"
---
# <a name="determine-whether-to-implement-a-source-control-vspackage"></a>Určete, jestli se má implementovat balíčku VSPackage správy zdrojového kódu
Tato část popisuje možnosti řízení moduly plug-in zdrojového kódu a balíčků VSPackage správy zdrojového kódu pro rozšíření řešení a nabízí rozsáhlé pokyny o výběru cesty vhodné integrace správy zdrojového kódu.

## <a name="small-source-control-solution-with-limited-resources"></a>Malé source řešení pro ovládací prvek s omezenými zdroji
 Pokud mají omezené prostředky a nemůže být burdened s nároky na zápis zdrojový ovládací prvek balíček, můžete vytvořit moduly plug-in založené na rozhraní API modulu Plug-in zdroje ovládacího prvku. To umožňuje pracovat souběžně s balíčky správy zdrojového kódu a můžete přepínat mezi ovládací prvek moduly plug-in zdrojového kódu a balíčky na vyžádání. Další informace najdete v tématu [registrace a výběr](../../extensibility/internals/registration-and-selection-source-control-vspackage.md).

## <a name="large-source-control-solution-with-a-rich-feature-set"></a>Velké source řešení pro ovládací prvek s bohatou sadou funkcí
 Pokud chcete implementovat řešení zdrojového ovládacího prvku, který poskytuje bohaté zdrojového ovládacího prvku modelu, který není dostatečně zachyceny pomocí rozhraní API modulu Plug-in zdroje ovládacího prvku, zvažte zdrojový balíček ovládací prvek jako cestu integrace. To platí zejména v případě, že místo toho by byly nahrazeny zdrojový balíček adaptér ovládací prvek (který komunikuje se ovládací prvek moduly plug-in zdrojového kódu a poskytuje základní zdroj ovládací prvek uživatelského rozhraní) s vlastním tak, aby bylo možné zpracovat události ovládacího prvku zdroje vlastní způsobem. Pokud už máte uspokojivé zdrojový ovládací prvek uživatelského rozhraní a chcete zachovat ve [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], možnosti správy zdrojového kódu balíček umožňuje udělat přesně takhle. Zdrojový ovládací prvek balíček není obecná a je určený výhradně pro použití s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí.

 Pokud chcete implementovat řešení zdrojového ovládacího prvku, který poskytuje flexibilitu a lepší kontrolu nad zdrojového ovládacího prvku logiky a uživatelského rozhraní, možná dáte přednost zdrojového ovládacího prvku balíček integrace trasy. Můžete:

1. Zaregistrovat vlastní ovládací prvek zdroje balíčku VSPackage (viz [registrace a výběr](../../extensibility/internals/registration-and-selection-source-control-vspackage.md)).

2. Nahraďte výchozí zdrojový ovládací prvek uživatelského rozhraní vlastního uživatelského rozhraní (viz [vlastní uživatelské rozhraní](../../extensibility/internals/custom-user-interface-source-control-vspackage.md)).

3. Zadejte glyfy použít a zpracovat události piktogram Průzkumníka řešení (viz [piktogramů](../../extensibility/internals/glyph-control-source-control-vspackage.md)).

4. Zpracování událostí dotazu upravit a uložit dotaz (viz [dotaz upravit dotaz uložit](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md)).

## <a name="see-also"></a>Viz také:
- [Vytvoření modulu plug-in správy zdrojového kódu](../../extensibility/internals/creating-a-source-control-plug-in.md)