---
title: Visual Basic IntelliSense
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 903bfe0a0effe87ca3f56fcfca5044afdf17e347
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
ms.locfileid: "32425019"
---
# <a name="intellisense-for-visual-basic-code-files"></a>IntelliSense pro soubory s kódem jazyka Visual Basic

Editor kódu jazyka Visual Basic zdroj nabízí následující funkce IntelliSense:

## <a name="syntax-tips"></a>Syntaxe tipy

Syntaxe tipy zobrazení syntaxe příkazu, který zadáte. To je užitečné pro příkazy, jako například [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement).

## <a name="automatic-completion"></a>Automatické dokončování

- Dokončení na různých klíčová slova

     Pokud zadáte například `goto` a místa, IntelliSense zobrazí seznam definovaných popisky v rozevírací nabídce. Zahrnout další podporované klíčová slova `Exit`, `Implements`, `Option`, a `Declare`.

- Dokončení na `Enum` a `Boolean`

    Pokud příkaz bude odkaz na člena výčtu, IntelliSense zobrazí seznam členů `Enum`. V případě bude příkaz odkazujete `Boolean`, IntelliSense zobrazí rozevírací nabídky hodnotu true na false.

Dokončení může být vypnuto ve výchozím nastavení pomocí zrušením výběru **automatický seznam členů** z **Obecné** stránka vlastností v **jazyka Visual Basic** složky.

Dokončení můžete vyvolat ručně vyvoláním seznam členů, dokončení Word, nebo **Alt**+**šipka vpravo**. Další informace najdete v tématu [pomocí IntelliSense](../ide/using-intellisense.md).

## <a name="intellisense-in-zone"></a>IntelliSense v zóně

IntelliSense v zóně pomáhá jazyka Visual Basic vývojáře, kteří potřebují nasazovat aplikace pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] a jsou omezená na nastavení částečné důvěryhodnosti. Tato funkce:

- Umožní vám vybrat oprávnění, která bude aplikace spuštěna s.

- Rozhraní API pro zobrazení v zvolený zónu jako dostupné v seznamu členů a zobrazit rozhraní API, které vyžadují další oprávnění jako nedostupné.

Další informace najdete v tématu [zabezpečení přístupu kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md).

## <a name="filtered-completion-lists"></a>Filtrované seznamy dokončení

Seznamy dokončení IntelliSense v jazyce Visual Basic mít dva ovládací prvky karet umístěné v dolní části seznamy. **Běžné** kartu, která je standardně vybraná, zobrazí položky, které se nejčastěji používají k dokončení příkazu, který vytváříte. **Všechny** zobrazí všechny položky, které jsou k dispozici pro automatické dokončování, včetně těch, které jsou k dispozici také na kartě **běžné** kartě.

## <a name="see-also"></a>Viz také

- [Používání technologie IntelliSense](../ide/using-intellisense.md)