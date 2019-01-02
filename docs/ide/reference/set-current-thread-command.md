---
title: Nastavit aktuální vlákno – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- debug.setcurrentthread
helpviewer_keywords:
- Set Current Thread command
- Debug.SetCurrentThread command
ms.assetid: 9917ed1d-6c30-4d94-b2f0-69acce74f1b2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 03d253d9be0d8bf5456f1a436d45762d6f030f86
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53855335"
---
# <a name="set-current-thread-command"></a>Nastavit aktuální vlákno – příkaz
Nastaví zadaný podproces jako aktuální vlákno.

## <a name="syntax"></a>Syntaxe

```
Debug.SetCurrentThread index
```

## <a name="arguments"></a>Arguments
 `index`

 Povinný parametr. Vybere vlákno podle jejich indexu.

## <a name="example"></a>Příklad

```
>Debug.SetCurrentThread 1
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)