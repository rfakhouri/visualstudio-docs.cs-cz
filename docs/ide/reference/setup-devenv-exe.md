---
title: "devenv.exe instalační přepínač | Microsoft Docs"
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e37fe50eefc36e7b5396f396d2b614851a0bd9cb
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)

/ Setup přepínače příčiny sloučení prostředků metadata, která popisuje nabídek, panely nástrojů a příkaz skupin, ze všech dostupných VSPackages sady Visual Studio.

## <a name="syntax"></a>Syntaxe

```shell
devenv /setup
```

## <a name="remarks"></a>Poznámky

Tento přepínač nezadávaly žádné argumenty. `devenv /setup` Příkaz je obvykle zadána jako poslední krok procesu instalace. Použití `/setup` přepínač nespustí Visual Studio.

> [!NOTE]
> Je nutné spustit `devenv` jako správce, aby bylo možné používat `/setup` přepínače.

## <a name="example"></a>Příklad

Tento příklad ukazuje poslední krok v instalaci verze sady Visual Studio, která zahrnuje VSPackages.

```shell
devenv /setup
```

## <a name="see-also"></a>Viz také

[Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)