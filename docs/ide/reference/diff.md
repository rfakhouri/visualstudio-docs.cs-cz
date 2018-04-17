---
title: -Rozdílové | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 016de0a06615caab723f83900e8bd4103cb142b1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="diff"></a>/Diff
Porovná dva soubory. Rozdíly jsou zobrazeny v okně speciální Visual Studio.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /Diff SourceFile, TargetFile, [SourceDisplayName],[TargetDisplayName]  
```  
  
## <a name="arguments"></a>Arguments  
 `SourceFile`  
 Požadováno. Úplná cesta a název první soubor, který se má porovnat.  
  
 `TargetFile`  
 Požadováno. Úplná cesta a název druhého souboru, který se má porovnat  
  
 `SourceDisplayName`  
 Volitelné. Zobrazovaný název první soubor.  
  
 `TargetDisplayName`  
 Volitelné. Zobrazovaný název druhý soubor.