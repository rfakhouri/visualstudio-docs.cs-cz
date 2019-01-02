---
title: Přidat existující projekt – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- file.addexistingproject
helpviewer_keywords:
- Add Existing Project command
- File.AddExistingProject
ms.assetid: 71cf3e31-c76b-405b-ad6a-1b1bc654bd40
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a5b0579037d31cf88de32f4fabda531d92c1b61
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53880452"
---
# <a name="add-existing-project-command"></a>Přidat existující projekt – příkaz
Přidá existující projekt do aktuálního řešení.

## <a name="syntax"></a>Syntaxe

```cmd
File.AddExistingProject filename
```

## <a name="arguments"></a>Arguments
 `filename` Volitelné. Úplnou cestu a projekt název, pomocí rozšíření projektu pro přidání do řešení.

 Pokud `filename` argument obsahuje mezery, musí být uzavřen v uvozovkách.

 Pokud není zadán žádný název souboru, bude příkaz tak, že tento uživatel může vybrat projekt otevřete dialogové okno souboru.

## <a name="remarks"></a>Poznámky
 Automatické dokončování, pokusí se najít správnou cestu a název souboru během psaní.

## <a name="example"></a>Příklad
 V tomto příkladu přidá [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] projektu, projekt testproject1 vyžaduje, do aktuálního řešení.

```cmd
>File.AddExistingProject "c:\visual studio projects\TestProject1.vbproj"
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)