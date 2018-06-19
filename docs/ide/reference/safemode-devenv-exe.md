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
ms.openlocfilehash: c2c678d7304c879cf42c24de9d83704971043676
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704145"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
Spustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] v nouzovém režimu, načítání výchozí prostředí a služeb.

## <a name="syntax"></a>Syntaxe

```cmd
devenv /SafeMode
```

## <a name="remarks"></a>Poznámky
 Tento přepínač zabrání všechny VSPackages třetích stran při načítání [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] spustí, čímž zajišťuje stabilní provádění.

## <a name="description"></a>Popis
 Následující příklad spustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] v nouzovém režimu.

## <a name="code"></a>Kód

```cmd
Devenv.exe /SafeMode
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)