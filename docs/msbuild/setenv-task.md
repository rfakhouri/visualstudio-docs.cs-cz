---
title: SETENV – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e2d9cec2c76b2159e14b1e7abe19b93ab91f6688
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/19/2018
ms.locfileid: "39153771"
---
# <a name="setenv-task"></a>SETENV – úloha
Nastaví nebo vymaže hodnotu proměnné zadané prostředí.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **SetEnv** úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**Jméno**|Vyžaduje **řetězec** parametru.<br /><br /> Název proměnné prostředí.|  
|**OutputEnvironmentVariable**|Volitelné **řetězec** výstupní parametr.<br /><br /> Obsahuje hodnotu, která je přiřazená k proměnné prostředí, která je zadána **název** parametru.|  
|**Předpona**|Povinné `Boolean` parametru.<br /><br /> Pokud `true`, zřetězí hodnoty **hodnotu** parametr před hodnotu proměnné prostředí, která je zadána **název** parametr a poté přiřadí výsledek do prostředí Proměnná. Pokud `false`, přiřadí pouze hodnotu **hodnotu** parametr do proměnné prostředí.|  
|**Cíl**|Volitelné **řetězec** parametru.<br /><br /> Určuje umístění, kde je uložen na proměnnou prostředí. Zadejte "User" nebo "Počítač".<br /><br /> Další informace najdete v tématu [EnvironmentVariableTarget výčet](https://msdn.microsoft.com/library/system.environmentvariabletarget(v=vs.110).aspx) na webu MSDN.|  
|**Hodnota**|Volitelné **řetězec** parametru.<br /><br /> Hodnota přiřazená k proměnné prostředí, která je zadána **název** parametru. Pokud **hodnotu** je prázdný a existuje proměnná, proměnná je Odstraněná. Pokud proměnná neexistuje, nedojde k žádné chybě i v případě, že operaci nejde provést.<br /><br /> Další informace najdete v tématu [Environment::SetEnvironmentVariable metoda](https://msdn.microsoft.com/library/96xafkes(v=vs.110).aspx) na webu MSDN.|  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)