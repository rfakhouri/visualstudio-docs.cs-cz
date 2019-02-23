---
title: -Command (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- Devenv, /Command switch
- /Command Devenv switch
- Command Devenv switch
ms.assetid: 13c20cd6-f09d-400a-8b7b-ecc266a32cef
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6daa21f9db7eef9a651577ad829d884dccf353dc
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717517"
---
# <a name="command-devenvexe"></a>/Command (devenv.exe)

Provede zadaný příkaz po spuštění integrovaného vývojového prostředí sady Visual Studio.

## <a name="syntax"></a>Syntaxe

```shell
devenv /Command CommandName
```

## <a name="arguments"></a>Arguments

*CommandName*

Povinný parametr. Úplný název příkazu sady Visual Studio nebo jeho alias uzavřený v dvojitých uvozovkách. Další informace o syntaxi příkazů a aliasů naleznete v tématu [příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md).

## <a name="remarks"></a>Poznámky

Po dokončení spuštění IDE spustí pojmenovaný příkaz.

::: moniker range="vs-2017"

Pokud použijete tento přepínač, rozhraní IDE nezobrazí úvodní stránky při spuštění.

::: moniker-end

Pokud doplněk vystavuje příkaz, můžete použít tento přepínač se spustit doplněk z příkazového řádku. Další informace najdete v tématu [jak: Řízení doplňků pomocí Správce doplňků](/previous-versions/xwdatdwh(v=vs.140)).

## <a name="example"></a>Příklad

První příklad spustí sadu Visual Studio a automaticky spustí makro otevřít oblíbené soubory.

V druhém příkladu se otevře karta integrovaného vývojového prostředí pro prohlížení a přejde na web Microsoft Docs.

Třetí příklad vytvoří nový soubor s názvem `some_file.cs` a otevře v editoru kódu.

```shell
devenv /command "Macros.MyMacros.Module1.OpenFavoriteFiles"

devenv /command "navigate https://docs.microsoft.com/"

devenv /command "nf some_file.cs"
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
- [Okno příkazového řádku](command-window.md)