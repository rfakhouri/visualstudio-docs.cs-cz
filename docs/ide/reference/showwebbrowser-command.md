---
title: ShowWebBrowser – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- view.showwebbrowser
helpviewer_keywords:
- ShowWebBrowser command
- View.ShowWebBrowser command
ms.assetid: c6a4fbd6-8e9d-45cc-8b2f-93990d065e78
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 14e2d6f2c753c56d1628d20e921b7dff2aa83471
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926013"
---
# <a name="showwebbrowser-command"></a>ShowWebBrowser – příkaz

Zobrazí adresu URL zadanou v okně webového prohlížeče buď v rámci integrovaného vývojového prostředí (IDE) nebo mimo prostředí IDE.

## <a name="syntax"></a>Syntaxe

```cmd
View.ShowWebBrowser URL [/new][/ext]
```

## <a name="arguments"></a>Arguments
`URL`

Povinný parametr. Adresa URL (Uniform Resource Locator) pro web

## <a name="switches"></a>Přepínače
/new

Volitelné. Určuje, že se stránka zobrazí v nové instanci webového prohlížeče.

/ext

Volitelné. Určuje, že se stránka zobrazí ve výchozím webovém prohlížeči mimo rozhraní IDE.

## <a name="remarks"></a>Poznámky
Alias pro příkaz **ShowWebBrowser –** je **Navigate** nebo **NAV**.

## <a name="example"></a>Příklad
Následující příklad zobrazuje domovskou stránku Microsoft Docs ve webovém prohlížeči mimo rozhraní IDE. Pokud je již otevřena instance webového prohlížeče, je použita. v opačném případě se spustí nová instance.

```cmd
>View.ShowWebBrowser https://docs.microsoft.com /ext
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)