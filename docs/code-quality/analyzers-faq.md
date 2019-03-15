---
title: EditorConfig a analyzátory
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- analyzers, faq
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bec9296f15c48cf3b327c78cd0ce7d57adafa002
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57875081"
---
# <a name="analyzers-faq"></a>Analyzátory – nejčastější dotazy

Tato stránka obsahuje odpovědi na některé časté otázky ke správě analyzátory Roslyn v sadě Visual Studio.

## <a name="roslyn-analyzers-versus-editorconfig"></a>Analyzátory Roslyn a .editorconfig

**Q**: Mám použít analyzátory Roslyn nebo .editorconfig pro styl kódu?

**A**: Analyzátory Roslyn a soubory .editorconfig fungovat ručně v rukou. Při definování kódu styly [v souboru .editorconfig](../ide/editorconfig-code-style-settings-reference.md) nebo [textový editor možnosti](../ide/code-styles-and-quick-actions.md) stránky, ve skutečnosti konfigurujete analyzátory Roslyn, které jsou součástí sady Visual Studio. EditorConfig soubory můžete také použít k nakonfigurovat některé balíčky třetích stran analyzátoru, jako jsou například [analyzátory FxCop](configure-fxcop-analyzers.md).

## <a name="editorconfig-versus-rule-sets"></a>EditorConfig oproti sady pravidel

**Q**: Můžu nakonfigurovat Moje analyzátory pomocí sady pravidel nebo pomocí souboru .editorconfig?

**A**: Sady pravidel a soubory .editorconfig jsou vzájemně se vylučující způsoby, jak nakonfigurovat analyzátory. Můžou existovat společně. [Sady pravidel](analyzer-rule-sets.md) umožňují povolení a zákaz pravidel a nastavení jejich závažnosti. EditorConfig soubory nabízejí další způsoby, jak nakonfigurovat pravidla. Pro analyzátory FxCop, vám umožní soubory .editorconfig [definovat typy kódu k analýze](fxcop-analyzer-options.md). Pro analyzátory, které jsou součástí sady Visual Studio, vám umožní soubory .editorconfig [definovat styly upřednostňované kód](../ide/editorconfig-code-style-settings-reference.md) pro základ kódu.

Kromě sady pravidel a soubory .editorconfig některé analyzátorů třetích stran jsou nakonfigurovány pomocí textových souborů, které jsou označeny jako [další soubory](../ide/build-actions.md#build-action-values) pro C# a kompilátory jazyka Visual Basic.

> [!NOTE]
> EditorConfig soubory nelze použít ke konfiguraci pravidel pro analýzu statického kódu, zatímco sad pravidel můžete.

## <a name="analyzers-in-ci-builds"></a>Analyzátory ve službě průběžné integrované sestavení

**Q**: Fungují analyzátory v sestaveních nepřetržité integrace (CI)?

**A**: Ano. Pro analyzátory, které jsou nainstalované z balíčku NuGet, tato pravidla jsou [vynucují v okamžiku sestavení](roslyn-analyzers-overview.md#build-errors), včetně během sestavení CI. Analyzátory používá v konfiguraci pravidla dodržování CI sestavení z obou [sad pravidel](analyzer-rule-sets.md) a [soubory .editorconfig](configure-fxcop-analyzers.md). V současné době analyzátorů kódu, které jsou součástí Visual Studia nejsou k dispozici jako balíček NuGet, a proto nejsou tato pravidla v sestavení CI vynutitelné.

## <a name="ide-analyzers-versus-stylecop"></a>Integrované vývojové prostředí analyzátory oproti StyleCop

**Q**: Jaký je rozdíl mezi Visual Studio IDE, analyzátorů kódu a analyzátory StyleCop?

**A**: Integrované vývojové prostředí sady Visual Studio obsahuje integrované analyzátory, které vyhledávají oba problémy stylu a kvalitu kódu. Tato pravidla umožňují používat nové funkce jazyka, dokud budou už zavedená a zlepšit udržovatelnosti kódu. Integrované vývojové prostředí Analyzátory se průběžně aktualizují, s každou vydanou verzí sady Visual Studio.

[Analyzátory StyleCop](https://github.com/DotNetAnalyzers/StyleCopAnalyzers) jsou analyzátory třetích stran nainstalovaný jako balíček NuGet, která provádí kontrolu konzistence styl ve vašem kódu. Obecně platí StyleCop pravidla umožňují stanovit základní osobní preference pro kód bez doporučující styl jeden před jiným.

## <a name="analyzers-versus-static-code-analysis"></a>Analyzátory a statické analýzy kódu

**Q**: Jaký je rozdíl mezi analyzátory a statickou analýzu kódu?

**A**: Analyzátory analýzu zdrojového kódu v reálném čase a během kompilace, že statickou analýzu kódu analyzuje binární soubory po dokončení sestavení. Další informace najdete v tématu [analyzátory Roslyn a statickou analýzu kódu](roslyn-analyzers-overview.md#roslyn-analyzers-vs-static-code-analysis) a [analyzátory FxCop – nejčastější dotazy](fxcop-analyzers-faq.md).

## <a name="see-also"></a>Viz také:

- [Přehled analyzátory](roslyn-analyzers-overview.md)
- [EditorConfig nastavení konvence psaní kódu .NET](../ide/editorconfig-code-style-settings-reference.md)