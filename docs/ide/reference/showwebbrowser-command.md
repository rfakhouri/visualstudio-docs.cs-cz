---
title: ShowWebBrowser – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
ms.openlocfilehash: 018d94f2952b8169890377410ff00baf1a80fd41
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39176382"
---
# <a name="showwebbrowser-command"></a>ShowWebBrowser – příkaz

Zobrazí adresu URL zadanou v okně webového prohlížeče buď v rámci integrovaného vývojového prostředí (IDE) nebo mimo prostředí IDE.

## <a name="syntax"></a>Syntaxe

```cmd
View.ShowWebBrowser URL [/new][/ext]
```

## <a name="arguments"></a>Arguments
 `URL`

 Požadováno. Adresa URL (Uniform Resource Locator) pro web.

## <a name="switches"></a>Přepínače
 / Nový

 Volitelné. Určuje, že se zobrazí v nové instanci webového prohlížeče.

 /ext

 Volitelné. Určuje, že se zobrazí ve webovém prohlížeči výchozí mimo rozhraní IDE.

## <a name="remarks"></a>Poznámky
 Alias **showwebbrowser –** příkaz je **přejděte** nebo **nav**.

## <a name="example"></a>Příklad
 Následující příklad zobrazí domovská stránka MSDN Online ve webovém prohlížeči mimo rozhraní IDE. Pokud instance webového prohlížeče je už otevřená, je použit. v opačném případě se spustí novou instanci.

```cmd
>View.ShowWebBrowser http://msdn.microsoft.com /ext
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)