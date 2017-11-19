---
title: "SetEnv – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.task.setenv
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
caps.latest.revision: "6"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 0223d57cf4c16166149b1fc9e8903f563b724d20
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
|**Cíl**|Volitelné **řetězec** parametr.<br /><br /> Určuje umístění, kde jsou uložené proměnné prostředí. Zadejte "`User`"nebo"`Machine`".<br /><br /> Další informace najdete v tématu "EnvironmentVariableTarget výčtu" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**Hodnota**|Volitelné **řetězec** parametr.<br /><br /> Hodnotu přiřazenou proměnné prostředí, která je zadána **název** parametr. Pokud **hodnota** je prázdná a proměnná existuje, je-li odstranit proměnnou. Pokud proměnná neexistuje, nedojde k žádné chybě Přestože operaci nelze provést.<br /><br /> Další informace najdete v tématu "Environment::SetEnvironmentVariable způsob" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)