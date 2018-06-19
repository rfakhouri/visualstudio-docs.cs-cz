---
title: – Příkaz (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /command switch
- /command Devenv switch
ms.assetid: 13c20cd6-f09d-400a-8b7b-ecc266a32cef
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c21402c3b2b71372aaf170c68c65777eba4e95bf
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33703743"
---
# <a name="command-devenvexe"></a>/Command (devenv.exe)
Provede zadaný příkaz po spuštění [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE).

## <a name="syntax"></a>Syntaxe

```cmd
devenv /command CommandName
```

## <a name="arguments"></a>Arguments
 `CommandName` Vyžaduje se. Úplný název [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] příkaz nebo jeho alias uzavřena v uvozovkách. Další informace o příkazu a alias syntaxi najdete v tématu [příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md).

## <a name="remarks"></a>Poznámky
 Po dokončení spuštění prostředí IDE provede příkaz s názvem. Pokud chcete použít tento přepínač, rozhraní IDE nejsou zobrazeny [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] – úvodní stránka při spuštění.

 Pokud doplněk zpřístupní příkaz, můžete tento přepínač pro spuštění add-in z příkazového řádku. Další informace najdete v tématu [postupy: řízení doplňky s použitím správce Add-In](http://msdn.microsoft.com/Library/4f60444a-cb48-4cdb-8df4-941f6419aeeb).

## <a name="example"></a>Příklad
 Tento příklad spustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a automaticky spustí makro otevřených souborů oblíbených položek.

```cmd
devenv /command "Macros.MyMacros.Module1.OpenFavoriteFiles"
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)