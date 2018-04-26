---
title: -SafeMode (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eaf137b699b7a02a0ee79099e937767262fce4e9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
Spustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] v nouzovém režimu, načítání výchozí prostředí a služeb.

## <a name="syntax"></a>Syntaxe

```
devenv /SafeMode
```

## <a name="remarks"></a>Poznámky
 Tento přepínač zabrání všechny VSPackages třetích stran při načítání [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] spustí, čímž zajišťuje stabilní provádění.

## <a name="description"></a>Popis
 Následující příklad spustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] v nouzovém režimu.

## <a name="code"></a>Kód

```
Devenv.exe /SafeMode
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)