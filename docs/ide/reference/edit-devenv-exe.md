---
title: -Upravit (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /edit switch
- /Edit Devenv swtich
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22c5aeffae35a4202577cf8065b76b1968616355
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704288"
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)
Zadaný soubor se otevře v existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="syntax"></a>Syntaxe

```cmd
Devenv /edit [file1[ file2]]
```

## <a name="arguments"></a>Arguments
 `file1`

 Volitelné. Soubor otevřete v existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Pokud není žádná instance [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] existuje, zjednodušené okno rozložení a je vytvořena nová instance a `file1` je otevřen v nové instance.

 `file2`

 Volitelné. Jeden nebo více dalších souborů, otevřete v existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="remarks"></a>Poznámky
 Pokud není zadán žádný soubor a je existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] obdrží fokus. Pokud není zadán žádný soubor a neexistuje žádná existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], novou instanci třídy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je vytvořena s rozložení zjednodušené okna.

 Pokud existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je v modální stavu, například, pokud [dialogové okno Možnosti](../../ide/reference/options-dialog-box-visual-studio.md) otevřete, bude soubor otevřete v existující instanci, kdy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ukončí modální stavu.

## <a name="example"></a>Příklad
 Tento příklad otevře soubor `MyFile.cs` v existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nebo soubor se otevře v nové instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Pokud ještě neexistuje.

```cmd
devenv /edit MyFile.cs
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)