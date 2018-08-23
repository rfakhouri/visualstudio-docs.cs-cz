---
title: SETENV – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
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
manager: ghogen
ms.openlocfilehash: ccd67a4bf70e05f0661277db05430615afbcfdad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671543"
---
# <a name="setenv-task"></a>SetEnv – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [SETENV – úloha](https://docs.microsoft.com/visualstudio/msbuild/setenv-task).  
  
  
Nastaví nebo vymaže hodnotu proměnné zadané prostředí.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **SetEnv** úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**Jméno**|Vyžaduje **řetězec** parametru.<br /><br /> Název proměnné prostředí.|  
|**OutputEnvironmentVariable**|Volitelné **řetězec** výstupní parametr.<br /><br /> Obsahuje hodnotu, která je přiřazená k proměnné prostředí, která je zadána **název** parametru.|  
|**Předpona**|Povinné `Boolean` parametru.<br /><br /> Pokud `true`, zřetězí hodnoty **hodnotu** parametr před hodnotu proměnné prostředí, která je zadána **název** parametr a poté přiřadí výsledek do prostředí Proměnná. Pokud `false`, přiřadí pouze hodnotu **hodnotu** parametr do proměnné prostředí.|  
|**Cíl**|Volitelné **řetězec** parametru.<br /><br /> Určuje umístění, kde je uložen na proměnnou prostředí. Zadejte "`User`"nebo"`Machine`".<br /><br /> Další informace najdete v tématu "EnvironmentVariableTarget výčet" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**Hodnota**|Volitelné **řetězec** parametru.<br /><br /> Hodnota přiřazená k proměnné prostředí, která je zadána **název** parametru. Pokud **hodnotu** je prázdný a existuje proměnná, proměnná je Odstraněná. Pokud proměnná neexistuje, nedojde k žádné chybě i v případě, že operaci nejde provést.<br /><br /> Další informace najdete v tématu "Environment::SetEnvironmentVariable metoda" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)



