---
title: Formátování kódu jazyka Python
description: Jak automaticky formátovat kód Python v sadě Visual Studio, včetně mezery, příkazy, zabalení a komentáře.
ms.custom: ''
ms.date: 07/12/2017
ms.technology:
- devlang-python
dev_langs:
- python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: bd6264c42d8bd4f585d4166fa7cc46b621aa52cc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="formatting-python-code"></a>Formátování kódu jazyka Python

Visual Studio vám umožní rychle přeformátovat kód tak, aby odpovídala předem nakonfigurované možnosti formátování.

- Chcete-li formátovat výběr: vyberte **Upravit > Upřesnit > Výběr formátu** nebo stiskněte klávesu Ctrl + E, F.
- K formátování celý soubor: vyberte **Upravit > Upřesnit > Formátovat dokument** nebo stiskněte klávesu Ctrl + E, D.

Možnosti se konfigurují pomocí **nástroje > Možnosti > textový Editor > Python > formátování** a jeho vnořené karty. Je nutné vybrat **zobrazit všechna nastavení** pro tyto možnosti se objeví:

![Python formátování možnosti v sadě Visual Studio](media/options-editor-formatting.png)

Možnosti formátování ve výchozím nastavení jsou nastavené tak, aby odpovídaly nadmnožinou [průvodci správným stylem období 8](http://www.python.org/dev/peps/pep-0008/). **Obecné** karta určuje, kdy je použit formátování; nastavení pro tři karty jsou popsané v tomto článku.

[Python podporují v sadě Visual Studio](installing-python-support-in-visual-studio.md) také přidá užitečné [zadejte komentář odstavce](#fill-comment-paragraph-command) příkaz **Upravit > Upřesnit** nabídky, jak je popsáno v další části.

## <a name="spacing"></a>Mezery

**Mezer** ovládací prvky, kde prostory se přidají nebo odebrat kolem různé jazykové konstrukty. Každá možnost má tři možné hodnoty:

- Zaškrtnutí: zajistí, že se použije mezery.
- Vymazat: Odebere všechny mezery.
- Neurčitém: ponechá původní formátování na místě.

Příklady pro různé možnosti jsou uvedeny v následujících tabulkách:

| Možnost definice třídy | Zaškrtnutí | Vymazat |
| --- | --- | --- | 
| Vložení mezery mezi deklaraci třídy názvu a seznam základny | `class X (object): pass` | `class X(object): pass` | 
| Vložení mezery v uvozovkách seznamu základny | `class X( object ): pass` | `class X(object): pass` |
| Vložení mezery v uvozovkách seznamu prázdný základny | `class X( ): pass` | `class X(): pass` |

<br/>

| Definice funkcí – možnost | Zaškrtnutí | Vymazat |
| --- | --- | --- |
| Vložení mezery mezi deklaraci funkce název a seznam parametrů | `def X (): pass` | `def X(): pass` | 
| Vložení mezery v uvozovkách seznamu parametr | `def X( a, b ): pass` | `def X(a, b): pass` |
| Vložení mezery v uvozovkách seznamu prázdný parametr | `def X( ): pass` | `def X(): pass` |
| Vložení mezer kolem '=' v výchozí hodnoty parametrů | `includes X(a = 42): pass` | `includes X(a=42): pass` |
| Vložit místo před a za operátory návratový poznámky | `includes X() -> 42: pass` | `includes X()->42: pass` |

<br/>

| Možnost operátory | Zaškrtnutí | Vymazat |
| --- | --- | --- |
| Vložení mezer kolem binární operátory | `a + b` | `a+b` |
| Vložení mezer kolem přiřazení | `a = b` | `a=b` |

<br/>

| Možnost mezery výraz | Zaškrtnutí | Vymazat |
| --- | --- | --- |
| Vložení mezery mezi volání funkce název a seznam argumentů | `X ()` | `X()` |
| Vložení mezery v uvozovkách seznamu prázdný argument | `X( )` | `X()` |
| Vložení mezery v uvozovkách seznamu argumentů | `X( a, b )` | `X(a, b)` |
| Vložení mezery v závorkách výrazu | `( a )` | `(a)` |
| Vložení mezery v uvozovkách prázdný řazené kolekce členů | `( )` | `()` |
| Vložení mezery v uvozovkách řazené kolekce členů | `( a, b )` | `(a, b)` |
| Vložit prostor v rámci prázdný hranaté závorky | `[ ]` | `[]` |
| Vložení mezer v rámci hranaté závorky seznamů | `[ a, b ]` | `[a, b]` |
| Vložení mezery před otevřete hranatá závorka | `x [i]` | `x[i]` |
| Vložit prostor v rámci hranaté závorky | `x[ i ]` | `x[i]` |

<br/>

## <a name="statements"></a>Příkazy

**Příkazy** možnosti řízení automatické přepisování různých příkazů do další Pythonic formuláře.

| Možnost | Před formátování | Po formátování |
| --- | --- | --- |
| Umístěte importovaných modulů na nový řádek | `import sys, pickle` | `import sys`<br/>`import pickle` |
| Odebrání nepotřebných středníkem | `x = 42;` | `x = 42` |
| Umístěte více příkazů na nové řádky | `x = 42; y = 100` | `x = 42`<br/>`y = 100` |

## <a name="wrapping"></a>Zabalení

**Zabalení** umožňuje nastavíte **maximální šířka komentář** (výchozí hodnota je 80). Pokud **zabalení komentáře, které jsou moc široké** je možnost nastavena, komentáře, které není delší než tento maximální šířka přeformátuje Visual Studio.

```python
# Wrapped to 40 columns
# There should be one-- and preferably
# only one --obvious way to do it.
```

```python
# Not-wrapped:
# There should be one-- and preferably only one --obvious way to do it.
```

## <a name="fill-comment-paragraph-command"></a>Zadejte příkaz odstavec komentář

**Upravit > Upřesnit > zadejte komentář odstavce** přeteče (Ctrl + E, P) a formáty komentář text, kombinace krátké řádky společně a rozdělení dlouho ty.

Příklad:

```python
# foo
# bar
# baz
```

změny:

```python
# foo bar baz
```

```python
# This is a very long long long long long long long long long long long long long long long long long long long comment
```

změny:

```python
# This is a very long long long long long long long long long long long long
# long long long long long long long comment
```
