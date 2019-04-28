---
title: -Edit (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- Edit Devenv switch
- Devenv, /Edit switch
- /Edit Devenv switch
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 26433d62a68b28450a56eee1282376733acfe55c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838799"
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)

Zadaný soubor se otevře v existující instanci sady Visual Studio.

## <a name="syntax"></a>Syntaxe

```shell
devenv /Edit [File1[ FileN]...]
```

## <a name="arguments"></a>Arguments

- *File1*

  Volitelné. Soubor otevřete v existující instanci sady Visual Studio. Pokud neexistuje žádná instance sady Visual Studio, se vytvoří novou instanci se zjednodušeným rozložením okna a otevře se nástroj *File1* v nové instanci.

- *FileN*

  Volitelné. Nejméně jeden další soubor otevřete v existující instanci sady Visual Studio.

## <a name="remarks"></a>Poznámky

Pokud soubor není zadána, získá existující instanci sady Visual Studio fokus. Pokud není určen žádný soubor a neexistuje žádná instance sady Visual Studio, nástroj vytvoří instanci se zjednodušeným rozložením okna.

Je-li existující instanci aplikace Visual Studio do modálního stavu, soubor se otevře v existující instanci když Visual Studio se ukončí modální stav. Například tato situace může nastat, když [dialogové okno Možnosti](../../ide/reference/options-dialog-box-visual-studio.md) je otevřený.

## <a name="example"></a>Příklad

První příklad otevře soubor `MyFile.cs` v existující instanci sady Visual Studio. Pokud instanci aplikace Visual Studio neexistuje, nástroj otevře soubor v nové instanci. Druhý příklad je podobné, s výjimkou toho, aby se otevřela tři soubory, nikoli pouze jeden soubor.

```shell
devenv /edit MyFile.cs

devenv /edit MyFile1.cs MyFile2.cs MyFile3.cs
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)