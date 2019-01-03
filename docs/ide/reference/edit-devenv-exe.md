---
title: -Edit (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Devenv, /edit switch
- /Edit Devenv switch
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0ccbd3a693313b870378021e6404424cfb11f199
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53907985"
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)
Zadaný soubor se otevře v existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="syntax"></a>Syntaxe

```cmd
Devenv /edit [file1[ file2]]
```

## <a name="arguments"></a>Arguments
 `file1`

 Volitelné. Soubor otevřete v existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Pokud žádná instance [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] existuje, se zjednodušeným rozložením okna, je vytvořena nová instance a `file1` se otevře v nové instanci.

 `file2`

 Volitelné. Nejméně jeden další soubor otevřete v existující instanci systému [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="remarks"></a>Poznámky
 Pokud není určen žádný soubor, a existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] získá fokus. Pokud není určen žádný soubor a neexistuje žádná existující instance [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], novou instanci třídy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vytvoření se zjednodušeným rozložením okna.

 Pokud existující instanci systému [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je v modálního stavu, například, pokud [dialogové okno Možnosti](../../ide/reference/options-dialog-box-visual-studio.md) je otevřete, bude soubor otevřít v existující instanci, kdy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ukončí modální stav.

## <a name="example"></a>Příklad
 Tento příklad otevře soubor `MyFile.cs` v existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nebo otevře soubor v nové instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Pokud ještě neexistuje.

```cmd
devenv /edit MyFile.cs
```

## <a name="see-also"></a>Viz také

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)