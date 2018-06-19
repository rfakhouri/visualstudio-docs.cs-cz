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
ms.openlocfilehash: 4beed25b1cdbc9f298df32743b9fec2e59fcdd8b
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704873"
---
# <a name="showwebbrowser-command"></a>ShowWebBrowser – příkaz
Zobrazí adresu URL, zadejte v okně webového prohlížeče buď v rámci integrované vývojové prostředí (IDE) nebo externí k prostředí IDE.

## <a name="syntax"></a>Syntaxe

```cmd
View.ShowWebBrowser URL [/new][/ext]
```

## <a name="arguments"></a>Arguments
 `URL`

 Požadováno. Adresa URL (Uniform Resource Locator) pro webovou stránku.

## <a name="switches"></a>Přepínače
 / new

 Volitelné. Určuje, že stránka se zobrazí v nové instanci webového prohlížeče.

 /ext

 Volitelné. Určuje, zda stránky se zobrazí ve webovém prohlížeči výchozí mimo prostředí IDE.

## <a name="remarks"></a>Poznámky
 Alias pro funkci **showwebbrowser –** příkaz je **přejděte** nebo **nav**.

## <a name="example"></a>Příklad
 Následující příklad zobrazuje na webu MSDN Online domovskou stránku ve webovém prohlížeči mimo prostředí IDE. Pokud je již spuštěna instance webového prohlížeče, použije se; v opačném případě se spustí novou instanci.

```cmd
>View.ShowWebBrowser http://msdn.microsoft.com /ext
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)