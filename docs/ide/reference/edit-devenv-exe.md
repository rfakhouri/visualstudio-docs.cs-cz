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
ms.openlocfilehash: 8f0eb7cab3b1bc764f663cd647811928510281e8
ms.sourcegitcommit: ba5e072c9fedeff625a1332f22dcf3644d019f51
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/31/2019
ms.locfileid: "66432014"
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

Pokud je více než jednu instanci sady Visual Studio otevřené, je soubor otevřený v naposledy otevřeným instance.

## <a name="example"></a>Příklad

První příklad otevře soubor `MyFile.cs` v existující instanci sady Visual Studio. Pokud instanci aplikace Visual Studio neexistuje, nástroj otevře soubor v nové instanci. Druhý příklad je podobné, s výjimkou toho, aby se otevřela tři soubory, nikoli pouze jeden soubor.

```shell
devenv /edit MyFile.cs

devenv /edit MyFile1.cs MyFile2.cs MyFile3.cs
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
