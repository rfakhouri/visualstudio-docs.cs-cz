---
title: SETENV – úloha | Dokumentace Microsoftu
ms.date: 11/05/2018
ms.topic: reference
f1_keywords:
- vc.task.setenv
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), tasks
- SetEnv task (MSBuild (Visual C++))
ms.assetid: fd9e4225-68cb-4608-8b27-468b0218c936
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 16a73ac066ff0b61570f0ed918308cf8874121d7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996515"
---
# <a name="setenv-task"></a>SETENV – úloha
Nastaví nebo vymaže hodnotu proměnné zadané prostředí.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry **SetEnv** úloh.

|Parametr|Popis|
|---------------|-----------------|
|**Název**|Vyžaduje **řetězec** parametru.<br /><br /> Název proměnné prostředí.|
|**OutputEnvironmentVariable**|Volitelné **řetězec** výstupní parametr.<br /><br /> Obsahuje hodnotu, která je přiřazená k proměnné prostředí, která je zadána **název** parametru.|
|**Prefix**|Povinné `Boolean` parametru.<br /><br /> Pokud `true`, zřetězí hodnoty **hodnotu** parametr před hodnotu proměnné prostředí, která je zadána **název** parametr a poté přiřadí výsledek do prostředí Proměnná. Pokud `false`, přiřadí pouze hodnotu **hodnotu** parametr do proměnné prostředí.|
|**Cíl**|Volitelné **řetězec** parametru.<br /><br /> Určuje umístění, kde je uložen na proměnnou prostředí. Zadejte "User" nebo "Počítač".<br /><br /> Další informace najdete v tématu [EnvironmentVariableTarget výčet](xref:System.EnvironmentVariableTarget).|
|**Hodnota**|Volitelné **řetězec** parametru.<br /><br /> Hodnota přiřazená k proměnné prostředí, která je zadána **název** parametru. Pokud **hodnotu** je prázdný a existuje proměnná, proměnná je Odstraněná. Pokud proměnná neexistuje, nedojde k žádné chybě i v případě, že operaci nejde provést.<br /><br /> Další informace najdete v tématu [Environment::SetEnvironmentVariable metoda](xref:System.Environment.SetEnvironmentVariable%2A).|

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)