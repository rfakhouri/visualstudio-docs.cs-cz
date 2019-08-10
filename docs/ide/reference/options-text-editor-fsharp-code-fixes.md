---
title: Možnosti, textový editor, F#, opravy kódu
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.F%2523.Code_Fixes
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: a73991702455fab54baf868499634e1a4f5bbf48
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68870749"
---
# <a name="options-text-editor--f--code-fixes"></a>Nastavení Editor textu > F# > opravy kódu

Pomocí stránky možnosti oprav kódu můžete určit nastavení, které může pomáhat identifikovat chyby kódu a nabízet řešení. Chcete-li získat přístup k této stránce Možnosti, zvolte**možnost** **nástroje** > a pak zvolte možnost**opravy kódu** **editoru** > **F#**  > textu.

## <a name="code-fixes"></a>Opravy kódu

- **Zjednodušit názvy (odebrat nepotřebné kvalifikátory)**

  Pokud je toto políčko zaškrtnuté, plně kvalifikované názvy budou zjednodušeny, pokud není potřebná kvalifikace, například pro člena často používaného oboru názvů.

- **Vždy umístit otevřené příkazy na nejvyšší úroveň**

  Pokud je toto políčko zaškrtnuté a zadáte `open` příkaz v kódu, je umístěn na nejvyšší úrovni.

- **Odebrat nepoužívané otevřené příkazy**

  Pokud je toto políčko zaškrtnuté, dokumenty se analyzují pro nepoužité `open` příkazy a v [rychlé akci](../quick-actions.md) se zobrazí akce, která odebere všechny nepoužité `open` příkazy.

- **Analyzovat a navrhovat opravy pro nepoužívané hodnoty**

  Pokud je toto zaškrtávací políčko zaškrtnuto, nástroj rozpozná hodnotu, která není v kódu použita. Pokud pak najedete na nepoužitou hodnotu, doporučí se způsob, jakým můžete použít hodnotu.

## <a name="see-also"></a>Viz také:

- [Obecné, Prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)
- [Nalezení změn kódu a další historie pomocí CodeLensu](../../ide/find-code-changes-and-other-history-with-codelens.md)
