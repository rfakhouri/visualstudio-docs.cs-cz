---
title: "Formátování kódu jazyka Python v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 80e23d4e3973590d5046468e9efb826afd1417d5
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/01/2017
---
# <a name="formatting-python-code"></a>Formátování kódu jazyka Python

Visual Studio vám umožní rychle přeformátovat kód tak, aby odpovídala předem nakonfigurované možnosti formátování.

- Chcete-li formátovat výběr: vyberte **Upravit > Upřesnit > Výběr formátu** nebo stiskněte klávesu Ctrl + E, F.
- K formátování celý soubor: vyberte **Upravit > Upřesnit > Formátovat dokument** nebo stiskněte klávesu Ctrl + E, D.

Možnosti se konfigurují pomocí **nástroje > Možnosti > textový Editor > Python > formátování** a jeho vnořené karty a ve výchozím nastavení jsou nastavené tak, aby odpovídaly nadmnožinou [průvodci správným stylem období 8](http://www.python.org/dev/peps/pep-0008/). **Obecné** karta určuje, kdy je použit formátování; nastavení tři karty jsou popsaná v tomto tématu.

[Python podporují v sadě Visual Studio](installation.md) také přidá užitečné [zadejte komentář odstavce](#fill-comment-paragraph-command) příkaz **Upravit > Upřesnit** nabídky, jak je popsáno následujících.

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