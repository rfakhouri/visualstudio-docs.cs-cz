---
title: "devenv.exe instalační přepínač | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 93f03de74540d130d66ce123b355691e0828b93e
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)

/ Setup přepínače příčiny sloučení prostředků metadata, která popisuje nabídek, panely nástrojů a příkaz skupin, ze všech dostupných VSPackages sady Visual Studio.

## <a name="syntax"></a>Syntaxe

```
devenv /setup
```

## <a name="remarks"></a>Poznámky

Tento přepínač nezadávaly žádné argumenty. `devenv /setup` Příkaz je obvykle zadána jako poslední krok procesu instalace. Použití `/setup` přepínač nespustí Visual Studio.

Je nutné spustit `devenv` jako správce, aby bylo možné používat [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) a [/installvstemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) přepínače.

## <a name="example"></a>Příklad

Tento příklad ukazuje poslední krok v instalaci verze sady Visual Studio, která zahrnuje VSPackages.

```
devenv /setup
```

## <a name="see-also"></a>Viz také

[Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)