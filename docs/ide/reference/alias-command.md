---
title: Alias – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- tools.alias
helpviewer_keywords:
- aliases, Visual Studio commands
- commands, aliases
- Tools.Alias command
- command aliases
- alias command
ms.assetid: bdf857df-b5d5-450f-8c10-a6fd4dccc130
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0072bbd770a6d4fa675010048f2d067eb0961d62
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59662540"
---
# <a name="alias-command"></a>Alias – příkaz
Vytvoří nový alias pro úplný příkaz, úplný příkaz a argumenty, nebo jiný alias.

> [!TIP]
> Zadáním `>alias` bez argumentů zobrazí aktuální seznam aliasů a jejich definice.

## <a name="syntax"></a>Syntaxe

```cmd
Tools.Alias [/delete] [/reset] [aliasname] [aliasstring]
```

## <a name="arguments"></a>Arguments
 `aliasname` Volitelné. Název pro nový alias. Pokud není zadána žádná hodnota pro `aliasname`, zobrazí se seznam aktuálních aliasů a jejich definice.

 `aliasstring` Volitelné. Úplný název příkazu nebo existující alias a všechny parametry, které chcete vytvořit jako alias. Pokud není zadána žádná hodnota pro `aliasstring`, název aliasu a řetězec aliasu pro zadaný alias se zobrazí.

## <a name="switches"></a>Přepínače
 / DELETE nebo/del nebo /d volitelné. Odstraní určený alias a odebere ji z automatického dokončování.

 / reset volitelné. Obnoví původní nastavení seznamu předdefinovaných aliasů. To znamená, že obnoví všechny předdefinované aliasy a odebere všechny aliasy definované uživatelem.

## <a name="remarks"></a>Poznámky
 Vzhledem k tomu, že aliasy představují příkazy, musí být umístěné na začátku příkazového řádku.

 Při vydávání tohoto příkazu byste měli zahrnout přepínače bezprostředně za příkaz, nikoli za aliasy, jinak bude přepínač samotný součástí řetězce aliasu.

 `/reset` Přepínač žádá o potvrzení před aliasů. Neexistuje krátký tvar `/reset`.

## <a name="examples"></a>Příklady
 Tento příklad vytvoří nový alias `upper`, pro kompletní příkaz Edit.MakeUpperCase.

```cmd
>Tools.Alias upper Edit.MakeUpperCase
```

 Tento příklad odstraní alias, `upper`.

```cmd
>Tools.alias /delete upper
```

 Tento příklad zobrazuje seznam všech aktuálních aliasů a definic.

```cmd
>Tools.Alias
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)