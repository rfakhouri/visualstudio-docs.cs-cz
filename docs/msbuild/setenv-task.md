---
title: SetEnv – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 01c939d3d7a7f503e3f43d1b11047f0105a3ffa3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="setenv-task"></a>SetEnv – úloha
Nastaví nebo odstraní hodnotu proměnné zadaného prostředí.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **SetEnv** úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**Jméno**|Požadované **řetězec** parametr.<br /><br /> Název proměnné prostředí.|  
|**OutputEnvironmentVariable**|Volitelné **řetězec** výstupní parametr.<br /><br /> Obsahuje hodnotu, která je přiřazena k proměnné prostředí, která je zadána **název** parametr.|  
|**Předpona**|Povinné `Boolean` parametr.<br /><br /> Pokud `true`, zřetězí hodnoty **hodnotu** parametr před hodnotu proměnné prostředí, která je zadána **název** parametr a poté přiřadí výsledek do prostředí Proměnná. Pokud `false`, přiřadí pouze hodnotu **hodnota** parametru do proměnné prostředí.|  
|**cíl**|Volitelné **řetězec** parametr.<br /><br /> Určuje umístění, kde jsou uložené proměnné prostředí. Zadejte "`User`"nebo"`Machine`".<br /><br /> Další informace najdete v tématu "EnvironmentVariableTarget výčtu" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**Hodnota**|Volitelné **řetězec** parametr.<br /><br /> Hodnotu přiřazenou proměnné prostředí, která je zadána **název** parametr. Pokud **hodnota** je prázdná a proměnná existuje, je-li odstranit proměnnou. Pokud proměnná neexistuje, nedojde k žádné chybě Přestože operaci nelze provést.<br /><br /> Další informace najdete v tématu "Environment::SetEnvironmentVariable způsob" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)