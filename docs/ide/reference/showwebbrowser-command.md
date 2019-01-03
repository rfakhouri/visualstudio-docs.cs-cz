---
title: ShowWebBrowser – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- view.showwebbrowser
helpviewer_keywords:
- ShowWebBrowser command
- View.ShowWebBrowser command
ms.assetid: c6a4fbd6-8e9d-45cc-8b2f-93990d065e78
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: df5983b0cbc33abe0f5919a93af1450394134a99
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53985823"
---
# <a name="showwebbrowser-command"></a>ShowWebBrowser – příkaz

Zobrazí adresu URL zadanou v okně webového prohlížeče buď v rámci integrovaného vývojového prostředí (IDE) nebo mimo prostředí IDE.

## <a name="syntax"></a>Syntaxe

```cmd
View.ShowWebBrowser URL [/new][/ext]
```

## <a name="arguments"></a>Arguments
 `URL`

 Povinný parametr. Adresa URL (Uniform Resource Locator) pro web.

## <a name="switches"></a>Přepínače
 / Nový

 Volitelné. Určuje, že se zobrazí v nové instanci webového prohlížeče.

 /ext

 Volitelné. Určuje, že se zobrazí ve webovém prohlížeči výchozí mimo rozhraní IDE.

## <a name="remarks"></a>Poznámky
 Alias **showwebbrowser –** příkaz je **přejděte** nebo **nav**.

## <a name="example"></a>Příklad
 Následující příklad zobrazí domovská stránka Microsoft Docs ve webovém prohlížeči mimo rozhraní IDE. Pokud instance webového prohlížeče je už otevřená, je použit. v opačném případě se spustí novou instanci.

```cmd
>View.ShowWebBrowser https://docs.microsoft.com /ext
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)