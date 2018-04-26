---
title: -Resetskippkgs – (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /ResetSkipPkgs Devenv switch
- Devenv, /ResetSkipPkgs switch
- ResetSkipPkgs switch
ms.assetid: 7ece64f9-cfa4-4b34-b0d9-1c338b9557b3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6199bf96bc631cf1018b2cb72a4d3c3cf7c703cc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="resetskippkgs-devenvexe"></a>/ResetSkipPkgs (devenv.exe)
Vymaže všechny možnosti tak, aby přeskočil načítání přidaných do VSPackages uživatelé chtějí předejít přetížení problém VSPackages a potom spustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="syntax"></a>Syntaxe

```
Devenv /ResetSkipPkgs
```

## <a name="remarks"></a>Poznámky
 Přítomnost značku SkipLoading zakáže načítání VSPackage; vymazání značky znovu povolí načítání VSPackage.

## <a name="example"></a>Příklad
 Následující příklad vymaže všechny SkipLoading značky.

```
Devenv.exe /ResetSkipPkgs
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)