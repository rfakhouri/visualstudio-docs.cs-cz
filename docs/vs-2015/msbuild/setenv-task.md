---
title: SETENV – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
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
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4c5066709002c815e2cdad549d424af549eb0bca
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54784419"
---
# <a name="setenv-task"></a>SetEnv – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Nastaví nebo vymaže hodnotu proměnné zadané prostředí.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **SetEnv** úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**Název**|Vyžaduje **řetězec** parametru.<br /><br /> Název proměnné prostředí.|  
|**OutputEnvironmentVariable**|Volitelné **řetězec** výstupní parametr.<br /><br /> Obsahuje hodnotu, která je přiřazená k proměnné prostředí, která je zadána **název** parametru.|  
|**Prefix**|Povinné `Boolean` parametru.<br /><br /> Pokud `true`, zřetězí hodnoty **hodnotu** parametr před hodnotu proměnné prostředí, která je zadána **název** parametr a poté přiřadí výsledek do prostředí Proměnná. Pokud `false`, přiřadí pouze hodnotu **hodnotu** parametr do proměnné prostředí.|  
|**Cíl**|Volitelné **řetězec** parametru.<br /><br /> Určuje umístění, kde je uložen na proměnnou prostředí. Zadejte "`User`"nebo"`Machine`".<br /><br /> Další informace najdete v tématu "EnvironmentVariableTarget výčet" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**Hodnota**|Volitelné **řetězec** parametru.<br /><br /> Hodnota přiřazená k proměnné prostředí, která je zadána **název** parametru. Pokud **hodnotu** je prázdný a existuje proměnná, proměnná je Odstraněná. Pokud proměnná neexistuje, nedojde k žádné chybě i v případě, že operaci nejde provést.<br /><br /> Další informace najdete v tématu "Environment::SetEnvironmentVariable metoda" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
