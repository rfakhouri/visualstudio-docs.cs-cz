---
title: Prostředí – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- tools.shell
helpviewer_keywords:
- exe files
- Shell command
- Tools.Shell command
- executables, running from Visual Studio
- .exe files
- Shell, launching exe files
- Visual Studio, executables from
ms.assetid: 737fda23-b852-45c4-a9fe-41cbce6ba70f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cb6bfc98d5ef6f7b3d3b6291ea55530325836d56
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68918950"
---
# <a name="shell-command"></a>Prostředí – příkaz
Spustí spustitelné programy v rámci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="syntax"></a>Syntaxe

```cmd
Tools.Shell [/command] [/output] [/dir:folder] path [args]
```

## <a name="arguments"></a>Arguments
`path`

Povinný parametr. Cesta a název souboru, který se má provést, nebo dokument, který se má otevřít Úplná cesta je povinná, pokud zadaný soubor není v jednom z adresářů proměnné prostředí PATH.

`args`

Volitelné. Všechny argumenty, které se mají předat vyvolanému programu.

## <a name="switches"></a>Přepínače
/CommandWindow [nebo]/Command [nebo]/c [or]/cmd

Volitelné. Určuje, že výstup pro spustitelný soubor je zobrazen v **příkazovém** okně.

/dir:`folder` [nebo]/d:`folder`

Volitelné. Určuje pracovní adresář, který má být nastaven při spuštění programu.

/OutputWindow [nebo]/Output [nebo]/out [or]/o

Volitelné. Určuje, že výstup pro spustitelný soubor je zobrazen v okně **výstup** .

## <a name="remarks"></a>Poznámky
Přepínače/dir/o/c je nutné zadat ihned po `Tools.Shell`. Cokoli, co je uvedeno po názvu spustitelného souboru, je předáno do něj jako argumenty příkazového řádku.

Předdefinovaný alias `Shell` lze použít `Tools.Shell`místo.

> [!CAUTION]
> `path` Pokud argument poskytuje cestu k adresáři a název souboru, měli byste uzavřít celou cestu do literálních uvozovek ("" "), jak je uvedeno v následujícím seznamu:

```cmd
Tools.Shell """C:\Program Files\SomeFile.exe"""
```

Každá sada tří dvojitých uvozovek ("" ") je interpretována `Shell` procesorem jako jeden znak dvojité uvozovky. Proto předchozí příklad ve skutečnosti předá následující řetězec cesty k `Shell` příkazu:

```cmd
"C:\Program Files\SomeFile.exe"
```

> [!CAUTION]
> Pokud nezadáte řetězec cesty v literálových uvozovkách ("" "), systém Windows použije pouze část řetězce, která je až do prvního prostoru. Pokud například řetězec cesty výše nebyl v uvozovkách uveden správně, systém Windows vyhledá soubor s názvem program umístěný ve složce C:\ kořenový adresář. Pokud byl spustitelný soubor C:\Program.exe skutečně k dispozici, dokonce i jeden nainstalovaný po nedovolené manipulaci, systém Windows se pokusí spustit tento program místo požadovaného programu "c:\Program Files\SomeFile.exe".

## <a name="example"></a>Příklad
Následující příkaz pomocí příkazu Xcopy. exe zkopíruje soubor `MyText.txt` `Text` do složky. Výstup z **příkazu** Xcopy. exe se zobrazí v okně příkazového řádku i v okně **výstup** .

```cmd
>Tools.Shell /o /c xcopy.exe c:\MyText.txt c:\Text\MyText.txt
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Okno Výstup](../../ide/reference/output-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)