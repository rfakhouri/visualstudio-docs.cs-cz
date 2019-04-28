---
title: Vcmessage – úloha | Dokumentace Microsoftu
ms.date: 06/27/2018
ms.topic: reference
f1_keywords:
- vc.task.vcmessage
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- VCMessage task (MSBuild (Visual C++))
- MSBuild (Visual C++), VCMessage task
ms.assetid: 956675fd-05dc-40b4-856f-616145103498
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d025fd1f71b67acbcd532232b36b55fd35e1f530
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62970754"
---
# <a name="vcmessage-task"></a>VCMessage – úloha
Protokoly upozornění a chybové zprávy během sestavení.

## <a name="remarks"></a>Poznámky
 Tato úloha pomáhá implementovat MSBuild pro Visual C++ a není určena k volání uživatelem. Další informace naleznete v tématu <xref:Microsoft.Build.Utilities.TaskLoggingHelper>.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry **vcmessage –** úloh.

|Parametr|Popis|
|---------------|-----------------|
|**Argumenty**|Volitelné **řetězec** parametru.<br /><br /> Středníkem oddělený seznam zpráv k zobrazení.|
|**Kód**|Vyžaduje **řetězec** parametru.<br /><br /> Číslo chyby, která kvalifikuje zprávy.|
|**Typ**|Volitelné **řetězec** parametru.<br /><br /> Určuje typ zprávy a vygenerovat. Zadejte buď "Upozornění" a vygenerovat upozornění, nebo "Chyba" generovat chybovou zprávu.|

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)